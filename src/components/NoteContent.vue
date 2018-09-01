<template>
  <div class="note-content">
    <textarea name="content" class="content" placeholder="Write some sticky contents.">{{content}}</textarea>
    <!-- TODO: menu button -->
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NoteContent extends Vue {
  @Prop() private content!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.note-content {
  width: 100%;
  height: calc(100% - 20px);
}
.content {
  width: 100%;
  height: 100%;
  resize: none;
  border: none;
  background-color: transparent;
  box-sizing: border-box;
  padding: 0;
}
</style>
