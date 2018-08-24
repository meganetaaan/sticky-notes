<template>
  <div class="note-head">
    <input type="text" class="title" :value="title">
    <!-- TODO: menu button -->
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NoteHead extends Vue {
  @Prop() private title!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.note-head {
  width: 100%;
}
.title {
  text-align: center;
  width: 100%;
  font-weight: bold;
  background-color: transparent;
  border: none;
}
</style>
