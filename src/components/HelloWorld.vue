<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{contador}}</h3>
    <section v-if="msgSecret">
      <h3>Mensagem Escondida S2</h3>
    </section>
    <br />
    <b-button variant="outline-success" @click="acrescentar()">Clique aqui</b-button>
    <span class="textoBtn">Para aumentar</span>
    <!--V-on pode ser substituido por "@" no exemplo acima ficou >> @click (V-on:click) -->
    <!--V-bind pode ser substituido por ":" -->
    <br />
    <br />
    <b-button variant="outline-success" @click="diminuir()">Clique aqui</b-button>
    <span class="textoBtn">Para diminuir</span>
  </div>
</template>

<script>
export default {
  methods: {
    acrescentar() {
      this.contador++;
      this.contador >= 10 ? (this.msgSecret = true) : null;
      //operador ternário com else null
    },
    diminuir() {
      this.contador--;
      this.contador < 10 ? (this.msgSecret = false) : null;
    }
  },
  data() {
    return {
      contador: 0,
      msgSecret: false
    };
  },
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.textoBtn {
  padding-left: 0.5rem;
}
</style>
