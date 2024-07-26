<script setup>
import { reactive } from 'vue';
import ProductList from '@/components/ProductList.vue';
import ProductAdd from '@/components/ProductAdd.vue';

const descrição = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmSenha: '',
  nascimento: '',
  endereco: '',
  estado: '',
  hobbies: '',
  linguagem: '',
  biografia: ''
});

function salvarPerfil(NovoPerfil) {
  Object.assign(perfil, NovoPerfil)
}

</script>

<template>
  <productAdd @enviarAuteracoes="salvarPerfil" />
  <ProductList :perfil="perfil" />
</template>

<style scoped></style>