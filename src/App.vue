<template>
  <section>
    <cabecalho :Valor="titulo" />
    <div class="container">
      <adicionar-tarefa v-on:adicionarTarefa="adicionarTarefa"/>
      <listar-tarefas :tarefas="tarefas" />
      <footer>
        <em>Altere aqui o titulo da sua lista de tarefas</em>
        <entrada-dados v-model="titulo" type="text"/>
      </footer>
    </div>
    <rodape />
  </section>
</template>

<script>
import Cabecalho from "@/components/Cabecalho";
import Rodape from "@/components/Rodape";
import ListarTarefas from "@/components/ListarTarefas";
import AdicionarTarefa from "@/components/AdicionarTarefa";
import EntradaDados from "@/components/templates/EntradaDados"


export default {
  name: "App",
  components: { Cabecalho, Rodape, ListarTarefas, AdicionarTarefa, EntradaDados },
  data() {
    return{
      titulo: "Minha lista de tarefas",
      tarefas: [
        { titulo: "Estudar", checked: false},
        { titulo: "Programar", checked: true},
      ],
    };
  },
  methods : {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false
      })
    },
  },
};
</script>

<style>
ul li {
  list-style: none;
}
.container{
  width: 40%;
  margin: 20px auto 0px auto;
}
.removed{
  color: gray;
}
.removed label {
  text-decoration: line-through;
}

</style>
