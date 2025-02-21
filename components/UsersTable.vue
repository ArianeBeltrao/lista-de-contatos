<script setup lang="ts">
import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table";
import { useRouter } from "vue-router";

const router = useRouter();

const goToEditPage = () => {
  router.push("/usuarios/editar-usuario");
};
</script>

<template>
  <Table>
    <TableHeader>
      <TableRow>
        <TableHead class="text-center"> </TableHead>
        <TableHead>Nome</TableHead>
        <TableHead class="text-center"> Data de nascimento </TableHead>
        <TableHead class="text-center">CPF</TableHead>

        <TableHead class="text-center"> Email </TableHead>
        <TableHead class="text-center"> Telefone </TableHead>
        <TableHead class="text-center"> Username </TableHead>
        <TableHead class="text-center"> </TableHead>
      </TableRow>
    </TableHeader>
    <TableBody>
      <TableRow>
        <TableCell class="text-center">
          <Badge class="px-6 min-w-20 text-center"> ADMIN </Badge>
        </TableCell>
        <TableCell>Bolinha</TableCell>
        <TableCell class="text-center"> 02/01/2020 </TableCell>
        <TableCell class="text-center"> 16578978709 </TableCell>
        <TableCell class="text-center"> email@email.com </TableCell>
        <TableCell class="text-center"> 3322 8716 </TableCell>
        <TableCell class="text-center"> bolinhaUser </TableCell>

        <TableCell class="text-center">
          <button
            class="cursor-pointer items-center text-stone-700 hover:bg-sky-300 rounded-full h-10 w-10"
            @click="goToEditPage"
          >
            <i class="pi pi-pencil cursor-pointer" style="font-size: 1rem"></i>
          </button>
        </TableCell>
      </TableRow>
    </TableBody>
  </Table>
</template>
