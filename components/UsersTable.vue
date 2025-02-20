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
        <TableCell>Bolinha</TableCell>
        <TableCell class="text-center"> 02/01/2020 </TableCell>
        <TableCell class="text-center"> 16578978709 </TableCell>
        <TableCell class="text-center"> email@email.com </TableCell>
        <TableCell class="text-center"> 3322 8716 </TableCell>
        <TableCell class="text-center"> bolinhaUser </TableCell>

        <TableCell class="text-center">
          <i class="pi pi-pencil cursor-pointer" style="font-size: 1rem"></i>
        </TableCell>
      </TableRow>
    </TableBody>
  </Table>
</template>
