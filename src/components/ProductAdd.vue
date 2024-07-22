<script setup>
  import { reactive } from 'vue';
  const emit = defineEmits(['adicionar']);
  const informa = reactive({
    nome: '',
    sobrenome: '',
    senha: '',
    confirmSenha: '',
    dataNasc: '',
    endereco: '',
    cidade: '',
    estado: '',
    hobbies: [],
    linguagens: '',
    bio: ''
  });
  function salvar() {
    if (informa.senha === '' || informa.confirmSenha === '') {
      alert('Os campo senha e confirmar senha são obrigadorios');
      return;
    }
    emit('adicionar', { ...informa });
  }


</script>
<template>
  <form @submit.prevent="salvar">
    <div>
      <label for="nome">Nome</label>
      <input type="text" id="nome" v-model="informa.nome" />
    </div>
    <div>
      <label for="preco">Preço</label>
      <input type="text" id="preco" v-model="informa.preco" />
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>
