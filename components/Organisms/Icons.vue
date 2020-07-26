<template>
  <div class="icons">
    <div class="icons_title">めにゅ〜</div>
    <div class="icons_container">
      <div class="icon_container tv" @click="movie">
        <img class="icon" src="~assets/img/items/tv.png" />
        <div class="icon_text">TV</div>
      </div>
      <div class="icon_container music" @click="music">
        <img class="icon" src="~assets/img/items/music.png" />
        <div class="icon_text">Love Music</div>
      </div>
      <div class="icon_container works" @click="works">
        <img class="icon" src="~assets/img/items/works.png" />
        <div class="icon_text">Works</div>
      </div>
      <div class="icon_container twitter" @click="twitter">
        <img class="icon" src="~assets/img/items/twitter.png" />
        <div class="icon_text">twitter</div>
      </div>
      <div class="icon_container insta" @click="goinsta">
        <img class="icon" src="~assets/img/items/instagram.png" />
        <div class="icon_text">instagram</div>
      </div>
      <div class="icon_container note" @click="note">
        <img class="icon" src="~assets/img/items/note.png" />
        <div class="icon_text">note</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue, PropSync, Emit } from "nuxt-property-decorator";

@Component({
  components: {}
})
export default class AppIcons extends Vue {
  @Emit("movie") public movie() {}
  @Emit("music") public music() {}
  @Emit("works") public works() {}
  @Emit("twitter") public twitter() {}
  @Emit("note") public note() {}

  public goinsta() {
    window.open("https://www.instagram.com/djtarako/?hl=ja");
  }
}
</script>

<style lang="stylus">
.icons {
    cursor: pointer;
    font-weight: 600;
    border: 10px solid rgb(255, 201, 201);
    padding-bottom: 10px;

    .icons_title {
        font-size: 12px;
        padding: 0 0 5px 0;
        background-color: rgb(255, 201, 201);
        text-align: center;
    }

    .icons_container {
        width: 200px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        align-items: center;

        .icon_container {
            margin: 20px 15px 0;
        }

        .icon {
            margin: 0 0px 0 0;
            max-width: 36px;
        }

        .icon_text {
            background-color: rgb(216, 215, 231);
            text-align: center;
            font-size: 14px;
            max-width: 76px;
        }
    }
}
</style>
