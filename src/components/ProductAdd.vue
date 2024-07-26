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
})


</script>
<template>
  <h1>Formulário</h1>
  <div class="container text-left">
    <div class="row">
      <div class="colLados text-center">
      </div>
      <div class="col">
        <div class="formulario">
          <form @submit.prevent="enviarDados">

            <div class="campo">
              <label for="">Nome:</label>
              <div class="linha">
                <input type="text" v-model="perfil.nome" placeholder="Digite seu nome">
              </div>
            </div>

            <div class="campo">
              <label for="">Email:</label>
              <div class="linha">
                <input type="email" v-model="perfil.email" placeholder="Digite seu email">
              </div>
            </div>

            <div class="campo">
              <label for="">Senha:</label>
              <div class="linha">
                <input type="password" v-model="perfil.senha" placeholder="Digite sua senha">
              </div>
            </div>

            <div class="campo">
              <label for="">Confirmação de Senha:</label>
              <div class="linha">
                <input type="password" v-model="perfil.confirmSenha" placeholder="Digite sua senha">
              </div>
            </div>

            <div class="campo">
              <label for="">Data de Nascimento:</label>
              <div class="linha">
                <input type="date" v-model="perfil.nascimento" placeholder="Data de Nascimento">
              </div>
            </div>

            <div class="campo">
              <label for="">Selecione seu Estado:</label>
              <div class="linha">
                <select name="estados" id="estados" v-model.lazy="estados.sigla">
                  <option v-for="(item, index) in estados" :value="item" :key="index"> {{ item }}
                  </option>
                </select>
              </div>
            </div>

            <div class="campo">
              <label for="">Endereço:</label>
              <div class="linha">
                <input type="text" v-model="perfil.endereco" placeholder="Digite seu endereco">
              </div>
            </div>

            <div class="campo">
              <label for="">Hobbies:</label>
              <div class="linha">
                <input type="text" v-model="perfil.hobbies" placeholder="Digite seus hobbies">
              </div>
            </div>

            <div class="campo">
              <label for="">Linguagem de programação:</label>
              <div class="linha">
                <input type="text" v-model="perfil.linguagem" placeholder="Digite sua linguagem de programação">
              </div>
            </div>

            <div class="campo">
              <label for="">Biografia:</label>
              <div class="linha">
                <input type="text" v-model="perfil.biografia" placeholder="Digite sua biografia">
              </div>
            </div>

            <button type="submit" id="botao" class="btn btn-primary">Mostrar</button>
          </form>
        </div>
      </div>
      <div class="colLados text-center">
      </div>
    </div>
  </div>
</template>