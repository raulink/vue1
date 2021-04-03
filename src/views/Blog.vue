<template>
  <Titulo texto="Titulo del Blog" />
  <button @click="consumirApi">Consumir Api</button>

  <div v-for="item in arrayBlog" :key="item.id">
    <router-link :to="`/blog/${item.id}`">
      {{ item.title }}
    </router-link>
  </div>
</template>

<script>
import Titulo from "../components/Titulo.vue";
export default {
  data() {
    return {
      arrayBlog: [],
    };
  },
  components: {
    Titulo,
  },
  methods: {
    async consumirApi() {
      try {
        const data = await fetch("https://jsonplaceholder.typicode.com/posts");
        const array = await data.json();

        this.arrayBlog = array;
        console.log(array);
      } catch (error) {}
    },
  },

  created() {
    this.consumirApi();
  },
};
</script>
