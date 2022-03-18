<template>
  <div id="app">
    <ol>
      <li v-for="todo in listTodo" :key="todo.id">
        {{ todo }}
      </li>
    </ol>
    <input type="text" v-model="todo" />
    <button @click="tambahkan(todo)">Tambahkan</button>
    <text-hebat :list-todo="listTodo.length >= 4"></text-hebat>
  </div>
</template>

<script>
import TextHebat from "@/components/TextHebat.vue";
export default {
  name: "App",
  components: {
    TextHebat,
  },
  data() {
    return {
      todo: "",
      listTodo: [],
    };
  },
  methods: {
    tambahkan(todo) {
      if (todo != "") {
        this.listTodo.push(todo);
        this.todo = "";
      }
    },
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
#app li {
  text-transform: capitalize;
}
</style>
