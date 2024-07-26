<script setup>
import { reactive } from 'vue';
const emit = defineEmits(['mudarAlteracoes']);
const regiao = [
{ name: 'AC' },
{ name: 'AL' },
{ name: 'AP' },
{ name: 'AM' },
{ name: 'BA' },
{ name: 'CE' },
{ name: 'DF' },
{ name: 'PE' },
{ name: 'PI' },
{ name: 'RJ' },
{ name: 'RN' },
{ name: 'RS' },
{ name: 'RO' },
{ name: 'RR' },
{ name: 'SC' },
{ name: 'SP' },
{ name: 'SE' },
{ name: 'TO' },
{ name: 'ES' },
{ name: 'GO' },
{ name: 'MA' },
{ name: 'MT' },
{ name: 'MS' },
{ name: 'MG' },
{ name: 'PA' },
{ name: 'PB' },
{ name: 'PR' },
];

const descrição = reactive ({
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
})

function enviarDados () {
  let error = false 
  if (!error) {
    emit('mudarAlteracoes', { ...perfil })
  }

}
</script>
<template>
  <h1>Formulário</h1>
    
</template>
