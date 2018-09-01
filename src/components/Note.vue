<template>
  <div class="note">
    <NoteHead :title="title"></NoteHead>
    <NoteContent :content="content"></NoteContent>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import NoteHead from './NoteHead.vue';
import NoteContent from './NoteContent.vue';

@Component({
  components: {
    NoteHead,
    NoteContent,
  },
})
export default class Note extends Vue {
  @Prop() private title!: string;
  @Prop() private content!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.note {
  background-color: pink;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  width: 100%;
  height: 100%;
}
</style>
