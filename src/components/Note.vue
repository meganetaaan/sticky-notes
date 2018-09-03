<template>
  <div @keydown.alt.78.prevent="add" class="note">
    <NoteHead v-on:add="add" v-on:remove="remove" :title="title"></NoteHead>
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
  private title: string = 'hoge';
  private content: string = 'fuga';

  private add(n: number) {
    this.title = this.title + n;
    const x = window.screenLeft + 50;
    const y = window.screenTop + 50;
    const w = 300;
    const h = 200;
    const child = window.open('.', '', `left=${x},top=${y},width=${w},height=${h}`);
    if (child != null) {
      const el = child.document.querySelector('.note-content>content');
      if (el != null) {
        const input = el as HTMLElement;
        input.focus();
      }
    }
  }

  private remove() {
    if (window.confirm('Delete this note?')) {
      window.close();
    }
  }
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
