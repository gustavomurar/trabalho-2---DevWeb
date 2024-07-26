<script setup>
import { reactive } from 'vue';
import ProductList from '@/components/ProductList.vue';
import ProductAdd from '@/components/ProductAdd.vue';

const perfil = reactive({
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

function salvarPerfil(novoPerfil) {
  Object.assign(perfil, novoPerfil)
}

</script>

<template>
  <productAdd @enviarAlteracoes="salvarPerfil" />
  <ProductList :perfil="perfil" />
</template>

<style scoped></style>