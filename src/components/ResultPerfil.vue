<script setup>
defineProps(['perfil'])
</script>

<template>
    <div class="resposta">
    <h1>Respostas</h1>
     <label for="">Nome:</label>
    <p>{{ perfil.nome }}</p>
    <label for="">Email:</label>
    <p>{{ perfil.email }}</p>
    <label for="">Senha:</label>
    <p>{{ perfil.senha }}</p>
    <label for="">Data de Nacimento:</label>
    <p>{{ perfil.nascimento }}</p>
    <label for="">Estado:</label>
    <p>{{ perfil.estados }}</p>
    <label for="">Cidade:</label>
    <p>{{ perfil.cidade }}</p>
    <label for="">Endereço:</label>
    <p>{{ perfil.endereco }}</p>
    <label for="">Hobbies:</label>
    <p>{{ perfil.hobbies }}</p>
    <label for="">Linguagem de Programação:</label>
    <p>{{ perfil.linguagem }}</p>
    <label for="">Biografia:</label>
    <p>{{ perfil.biografia }}</p>
</div>
</template>

<style scoped>
.resposta{
    background-color: rgb(208, 231, 154);
    width: 45%;

}
</style>

