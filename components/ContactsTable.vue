<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table";
</script>

<template>
  <Table>
    <TableHeader>
      <TableRow>
        <TableHead></TableHead>
        <TableHead></TableHead>
        <TableHead>Nome</TableHead>
        <TableHead class="text-center">CPF</TableHead>
        <TableHead class="text-center"> Endereço </TableHead>

        <TableHead class="text-center"> Tag </TableHead>
        <TableHead class="text-center"> Telefone </TableHead>
        <TableHead class="text-center"> Tipo de contato </TableHead>
        <TableHead class="text-center"></TableHead>
        <TableHead></TableHead>
        <TableHead></TableHead>
      </TableRow>
    </TableHeader>
    <TableBody>
      <TableRow>
        <TableCell class="text-center">
          <button class="cursor-pointer">
            <i class="pi pi-star" style="font-size: 1.5rem"></i>
          </button>
        </TableCell>
        <TableCell>
          <Avatar class="bg-blue-300">
            <AvatarImage
              src="https://github.com/radix-vue.png"
              alt="@radix-vue"
            />
            <AvatarFallback>CN</AvatarFallback>
          </Avatar>
        </TableCell>
        <TableCell>Bolinha</TableCell>
        <TableCell class="text-center"> 16578978709 </TableCell>
        <TableCell class="text-center"> Rua 1 </TableCell>
        <TableCell class="text-center">
          <Badge class="px-6 min-w-20 text-center bg-red-200"
            >Principal</Badge
          ></TableCell
        >
        <TableCell class="text-center"> 33223435 </TableCell>
        <TableCell class="text-center"> celular </TableCell>
        <TableCell class="text-center">
          <Badge variant="outline">Privado</Badge>
        </TableCell>
        <TableCell class="text-center">
          <i class="pi pi-pencil" style="font-size: 1rem"></i>
        </TableCell>
        <TableCell class="text-center">
          <DeleteDrawer title="Tem certeza que deseja excluir esse contato" />
        </TableCell>
      </TableRow>
    </TableBody>
  </Table>
</template>
