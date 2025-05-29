<script>
import AddTask from './components/AddTask.vue'

export default {
  components: { AddTask },
  data() {
    return {
      // variabili
    }
  },
  methods: {
    // metodi/funzioni
  }

}
</script>

<template>
  <div class="container">
    <h1>To Do App con Vue.Js</h1>

    <!-- componente: aggiunta dei task -->
    <AddTask />
    
    <!-- componente: lista dei task -->

  </div>  
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
