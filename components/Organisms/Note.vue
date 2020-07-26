<template>
  <div class="note">
    <div class="note_title_container">
      <div class="note_delete" @click="click">×</div>
      <div class="note_title">Djたらこ|fujii tatsuya</div>
    </div>
    <iframe
      class="note-embed"
      src="https://note.com/embed/notes/nf63c2229a4b8"
      style="border: 0; display: block; max-width: 100%; width: 494px; padding: 0px; margin: 0px 0px; position: static; visibility: visible;"
      height="400"
    ></iframe>
    <script
      async
      src="https://note.com/scripts/embed.js"
      charset="utf-8"
    ></script>
  </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue, Emit } from "nuxt-property-decorator";
import { Tweet, Moment, Timeline } from "vue-tweet-embed";

@Component({
  components: {
    "v-timeline": Timeline
  }
})
export default class Note extends Vue {
  @Emit("click") public click() {}
}
</script>

<style lang="stylus" scoped>
.note {
    width: 370px;
    height: 502px;
    border: 10px solid rgb(255, 201, 201);

    .note_title_container {
        background-color: rgb(255, 201, 201);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 0 5px;

        .note_delete {
            cursor: pointer;
            background-color: rgb(216, 215, 231);
            margin: 0 0px 0 10px;
            width: 30px;
            text-align: center;
            border-radius: 50%;
        }

        .note_title {
            font-weight: 600;
            font-size: 12px;
            padding: 0 20px 0 0;
        }
    }

    .note {
        width: 360px;
        height: 500px;
        background-color: #ffffff;
    }
}
</style>
