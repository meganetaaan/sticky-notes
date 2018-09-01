<template>
  <div id="app">
    <Note title="hoge" content="fuga"></Note>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Note from './components/Note.vue';

@Component({
  components: {
    Note,
  },
})
export default class App extends Vue {}
</script>

<style>
html,body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
</style>
