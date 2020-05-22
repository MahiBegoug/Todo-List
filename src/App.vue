<template>
  <div id="app" class="container py-5">
    <h1 class="fs-h1 text-center">
      My first Todo App!
    </h1>

    <TodoList/>
  </div>
</template>

<script>

import TodoList from "@/components/TodoList";
export default {
  name: 'app',
  components: {TodoList},
  data() {
    return {

    }
  },
  methods:{

  }
}
</script>

<style lang="scss">
  @import "./variables.scss";

  *, *::before, *::after {
    box-sizing: border-box;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: $vue-blue;
    margin-top: 60px;
  }

</style>
