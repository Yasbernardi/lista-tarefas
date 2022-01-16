<template>
<section>
  <cabecalho :titulo="titulo"/>
  <div class="container">
    <div>
      <input @keyup.enter="adicionarTarefa" v-model="NovaTarefa" type="text" />

      <span>
        <button @click="adicionarTarefa" >Adicionar</button>
      </span>

    </div>

    <ul class="lista">
      <li v-for="(tarefa, index) in tarefas" :key="index" :class="{ removed: tarefa.feito }">
        <input type="checkbox" v-model="tarefa.feito" />
        <label>{{ tarefa.titulo }}</label>
      </li>
    </ul>

    <div>
      Insira um titulo: 
      <input type="text" v-model="titulo">
    </div>
    
  </div>
</section>

</template>

<script>
import cabecalho from '@/components/cabecalho'
export default {
  name: "App",
  components: {cabecalho},
  data() {
    return {
      titulo: "Minha lista de tarefas",
      NovaTarefa: "",
      tarefas: [],
      erro: false
    };
  },
  methods: {
    adicionarTarefa() {
      if (this.NovaTarefa) {
        this.tarefas.push({
          titulo: this.NovaTarefa,
          feito: false,
        });
        this.NovaTarefa = "";
      }
      else{
        alert("Insira uma tarefa valida")
      }
    },
  },
};
</script>

<style>
body{
  font-family: 'Courier New', Courier, monospace;
  margin: 0;
  padding: 0;
}
.container {
  width: 40%;
  margin: auto;
  padding: 20px;
}
ul li {
  list-style: none;
}
.removed {
  color: gray;
}
.removed label {
  text-decoration: line-through;
}

</style>