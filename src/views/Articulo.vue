<template>
  <titulo texto="Titulo Articulo:" />
  <h2>Parametro {{ $route.params.id }}</h2>
    <h3>
        {{articulo.title}}
    </h3>
    <p>
        {{articulo.id}} -  {{articulo.body}}
    </p>

</template>

<script>
import Titulo from "../components/Titulo";
export default {
  data() {
    return {
      articulo: {},
    };
  },
  components: {
    Titulo,
  },
  methods: {
    async consumirArticulo() {
      try {
        const data = await fetch(
          `https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`
        );
        const array = await data.json();
        this.articulo = array
        console.log(array);
      } catch (error) {}
    },
  },
  created(){
      this.consumirArticulo()
  }
};
</script>
