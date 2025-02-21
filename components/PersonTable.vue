<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table";

const users = [
  {
    id: 1,
    nome: "Bolinha",
    cpf: "16578978709",
    foto: { url: "https://github.com/radix-vue.png" },
    endereco: {
      logradouro: "Rua 1",
      numero: 123,
      bairro: "Centro",
      cidade: "São Paulo",
      estado: "SP",
      cep: "01000-000",
      pais: "Brasil",
    },
  },
  {
    id: 2,
    nome: "Fofinho",
    cpf: "12345678901",
    foto: { url: "" },
    endereco: {
      logradouro: "Rua 2",
      numero: 456,
      bairro: "Bela Vista",
      cidade: "Rio de Janeiro",
      estado: "RJ",
      cep: "22000-000",
      pais: "Brasil",
    },
  },
];
</script>

<template>
  <Table>
    <TableHeader>
      <TableRow class="hover:bg-transparent">
        <TableHead rowspan="2"></TableHead>
        <TableHead rowspan="2">Nome</TableHead>
        <TableHead rowspan="2" class="text-center">CPF</TableHead>
        <TableHead colspan="7" class="text-center">Endereço</TableHead>
        <TableHead rowspan="2"></TableHead>
        <TableHead rowspan="2"></TableHead>
      </TableRow>
      <TableRow class="hover:bg-transparent">
        <TableHead class="text-center">Logradouro</TableHead>
        <TableHead class="text-center">Número</TableHead>
        <TableHead class="text-center">Bairro</TableHead>
        <TableHead class="text-center">Cidade</TableHead>
        <TableHead class="text-center">Estado</TableHead>
        <TableHead class="text-center">CEP</TableHead>
        <TableHead class="text-center">País</TableHead>
      </TableRow>
    </TableHeader>
    <TableBody>
      <TableRow v-for="(user, index) in users" :key="index">
        <TableCell>
          <Avatar class="bg-blue-300">
            <AvatarImage
              :src="user.foto?.url || 'https://github.com/radix-vue.png'"
              :alt="user.nome"
            />
            <AvatarFallback>{{ user.nome.charAt(0) }}</AvatarFallback>
          </Avatar>
        </TableCell>
        <TableCell>{{ user.nome }}</TableCell>

        <TableCell class="text-center">{{ user.cpf }}</TableCell>
        <TableCell class="text-center">{{
          user.endereco.logradouro
        }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.numero }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.bairro }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.cidade }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.estado }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.cep }}</TableCell>
        <TableCell class="text-center">{{ user.endereco.pais }}</TableCell>

        <TableCell class="text-center">
          <i class="pi pi-pencil" style="font-size: 1rem"></i>
        </TableCell>
        <TableCell class="text-center">
          <DeleteDrawer title="Tem certeza que deseja excluir essa pessoa" />
        </TableCell>
      </TableRow>
    </TableBody>
  </Table>
</template>
