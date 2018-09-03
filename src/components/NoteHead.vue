<template>
  <div class="note-head">
    <input type="text" class="title" placeholder="Write some sticky title." v-model="title">
    <div class="menu">
      <input @click="onClickAddButton" class="menu-button" type="button" value="+">
      <input @click="onClickRemoveButton" class="menu-button" type="button" value="🗑️">
    </div>
    <!-- TODO: menu button -->
  </div>
</template>

<script lang="ts">
import { Emit, Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class NoteHead extends Vue {
  @Prop() private title!: string;

  @Emit()
  private add(n: number) {
    // return nothing
  }

  @Emit()
  private remove() {
    // return nothing
  }

  private onClickAddButton(): void {
    this.add(1);
  }

  private onClickRemoveButton(): void {
    this.remove();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div.note-head {
  width: 100%;
  height: 20px;
  display: flex;
  flex-direction: row;
  background-color: salmon;
}
.title {
  text-align: center;
  width: 100%;
  font-weight: bold;
  background-color: transparent;
  border: none;
  flex-grow: 1;
}
.menu {
  display: flex;
  flex-direction: row;
}
.menu-button {
  background-color: transparent;
  border-style: none;
  cursor: pointer;
}
</style>
