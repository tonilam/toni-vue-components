<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <sortable-button field="test" v-model="order"></sortable-button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SortableButton from "./components/SortableButton";

export default {
  name: 'app',
  components: {
    HelloWorld,
    SortableButton,
  },
  data() {
    return {
      order: {
        field: null,
        order: null,
      },
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
