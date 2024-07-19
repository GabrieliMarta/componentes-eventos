<script setup>
import { ref } from 'vue';
  import ProductList from './components/ProductList.vue';

  const produtos = ref([
    { id: 1, nome: 'Produto 1', preco: 19.99 },
    { id: 2, nome: 'Produto 2', preco: 29.99 },
    { id: 3, nome: 'Produto 3', preco: 39.99 },
    {id: 4, nome: 'Produto 4', preco: 49.99 },
    {id: 5, nome: 'Produto 5', preco: 59.99 }
  ]);

  // excluir elemento 
  function removerItem(id) {
    const index = produtos.value.findIndex((produto) => produto.id === id);
    produtos.value.splice(index, 1);
  }
</script>

<template>
  <product-list :produtos="produtos" @remove="removerItem" />
</template>

<style scoped>

</style>
