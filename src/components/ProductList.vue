<script setup>
  const props = defineProps(['produtos']);
</script>

<template>
  <table>
    <thead>
      <tr>
        <th>Nome</th>
        <th>Preço</th>
        <th>Ações</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="produto in props.produtos" :key="produto.id">
        
        <td>{{ produto.nome }}</td>
        <td>{{ produto.preco }}</td>
        <td>
          <i class="mdi mdi-delete" @click="$emit('remove', produto.id)" />
        </td>
        
      </tr>
    </tbody>
  </table>
</template>

<style scoped>
  table {
    width: 50%;
    border-collapse: collapse;
  }

  th,
  td {
    border: 1px solid rgb(113, 58, 145);
    padding: 10px;
  }

  th {
    background-color: rgb(108, 139, 151);
  }

  tr {
    text-align: center;
  }

  tr i {
    cursor: pointer;
    font-size: larger;
  }
</style>