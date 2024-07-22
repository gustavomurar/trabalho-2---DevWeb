<script setup>
import { ref } from 'vue'

const infoma = ref({
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
})

let estados = [
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
  { name: 'PR' }
]

const enviar = ref(true)
</script>

<template>
  <main>
    <form v-if="enviar">
      <h1>EU:</h1>
      <div class="row mb-4">
        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input type="text" class="form-control" v-model="infoma.nome" placeholder="Nome" />
          </div>
        </div>

        <div class="col">
          <div data-mdb-input-init class="form-outline">
            <input
              type="text"class="form-control"v-model="infoma.sobrenome"placeholder="Sobrenome"/>
          </div>
        </div>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="email" class="form-control" v-model="infoma.email" placeholder="E-mail" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="password"class="form-control"v-model="infoma.senha"placeholder="Senha"/>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="password"class="form-control"v-model="infoma.confirmSenha"placeholder="Confirme sua senha"/>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <label for="dataNasc">Data de nascimento:</label>
        <input
          type="date"id="dataNasc"class="form-control"v-model="infoma.dataNasc"placeholder="Data de nascimento"/>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input
          type="text"class="form-control"v-model="infoma.endereco"placeholder="Endereço"/>
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <input type="text" class="form-control" v-model="infoma.cidade" placeholder="Cidade" />
      </div>

      <div data-mdb-input-init class="form-outline mb-4">
        <label class="form-label" for="estado">Estado:</label>
        <select class="form-select" id="estado" v-model="infoma.estado">
          <option v-for="estado of estados" :key="estado">{{ estado.name }}</option>
        </select>
      </div>

      <section class="opções">
        <p>Seus Hobbies:</p>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="checkbox"id="esportes"v-model="infoma.hobbies"value="esportes"/>
          <label class="form-check-label" for="esportes">Esportes</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="checkbox"id="musica"v-model="infoma.hobbies"value="musica"/>
          <label class="form-check-label" for="musica">Música</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="checkbox"id="leitura"v-model="infoma.hobbies"value="leitura"/>
          <label class="form-check-label" for="leitura">Leitura</label>
        </div>
      </section>

      <section class="opções">
        <p>Linguagem:</p>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="radio"id="js"value="js"v-model="infoma.linguagens"/>
          <label class="form-check-label" for="js">JavaScript</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="radio"id="swift"value="swift"v-model="infoma.linguagens"/>
          <label class="form-check-label" for="pyton">Swift</label>
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"type="radio"id="php"value="php"v-model="infoma.linguagens"/>
          <label class="form-check-label" for="php">PHP</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input"type="radio"id="c"value="c"v-model="infoma.linguagens"/>
          <label class="form-check-label" for="c">C</label>
        </div>
      </section>

      <div data-mdb-input-init class="form-outline mb-4">
        <textarea class="form-control"id="form6Example7"rows="4"placeholder="Biografia"v-model="infoma.bio"></textarea>
      </div>

      <button
        @click="enviar = false"
        data-mdb-ripple-init 
        type="button"class="btn btn-primary btn-block mb-4"
        >
        ENVIAR
      </button>
    </form>
    <section v-else>
      <div>
        <h2>INFOS:</h2>
        <p>Nome: {{ infoma.nome }}</p>
        <p>Sobrenome: {{ infoma.sobrenome }}</p>
        <p>E-mail: {{ infoma.email }}</p>
        <p>Senha: {{ infoma.senha }}</p>
        <p>Endereço: {{ infoma.endereco }}</p>
        <p>Cidade: {{ infoma.cidade }}</p>
        <p>Estados: {{ infoma.estado }}</p>
        <p>Hobbies: {{ infoma.hobbies }}</p>
        <p>Linguagem: {{ infoma.linguagens }}</p>
        <p>Biografia: {{ infoma.bio }}</p>  
        
      </div>

      <button
        @click="enviar = true"
        data-mdb-ripple-init
        type="button"
        class="btn btn-primary btn-block mb-4"
      >
        VOLTAR
      </button>
    </section>
  </main>
</template>


<style scoped>
  table {
    width: 50%;
    border-collapse: collapse;
  }

  th,
  td {
    border: 1px solid gray;
    padding: 10px;
  }

  th {
    background-color: lightgray;
  }

  tr {
    text-align: center;
  }

  tr i {
    cursor: pointer;
    font-size: larger;
  }
</style>