<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p :style="colorContador">Mi contador es {{ contador }}</p>
    <btn-disminuir> </btn-disminuir>
    <button @click="accionIncrementar">incrementar contador</button>
    <btn-accion :estado="true"> </btn-accion>
    <btn-accion :estado="false"> </btn-accion>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions } from "vuex";
import BtnDisminuir from "./BtnDisminuir.vue";
import BtnAccion from "./BtnAccion.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    BtnDisminuir,
    BtnAccion
  },
  computed: {
    ...mapState(["contador"]),

    colorContador() {
      return this.contador > 100 ? { color: "green" } : { color: "red" };
    },
  },
  methods: {
    ...mapActions(["accionIncrementar"]),
  },
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
</style>
