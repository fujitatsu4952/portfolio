<template>
  <div class="container">
    <div v-if="isMovie" class="top_movie" v-drag>
      <television @click="chageMovie" />
    </div>
    <div v-if="isMusic" class="top_music" v-drag>
      <music @click="chageMusic" />
    </div>
    <div v-if="isWorks" class="top_works" v-drag>
      <works @click="changeWorks" />
    </div>
    <div v-if="isTwitter" class="top_twitter" v-drag>
      <twitter @click="changeTwitter" />
    </div>
    <div v-if="isNote" class="top_note" v-drag>
      <note @click="changeNote" />
    </div>
    <div class="top_icons">
      <icons
        @movie="chageMovie"
        @music="chageMusic"
        @works="changeWorks"
        @twitter="changeTwitter"
        @note="changeNote"
      />
    </div>
  </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue } from "nuxt-property-decorator";
import drag from "@branu-jp/v-drag";
import Icons from "@/components/Organisms/Icons.vue";
import Television from "@/components/Organisms/Television.vue";
import Music from "@/components/Organisms/Music.vue";
import Works from "@/components/Organisms/Works.vue";
import Twitter from "@/components/Organisms/AppTwitter.vue";
import Note from "@/components/Organisms/Note.vue";

@Component({
  components: {
    Icons,
    Television,
    Music,
    Works,
    Twitter,
    Note
  },
  directives: {
    drag
  }
})
export default class start extends Vue {
  public isMovie: boolean = false;
  public isMusic: boolean = false;
  public isWorks: boolean = false;
  public isTwitter: boolean = false;
  public isNote: boolean = false;
  public chageMovie() {
    this.isMovie = !this.isMovie;
  }
  public chageMusic() {
    this.isMusic = !this.isMusic;
  }
  public changeWorks() {
    this.isWorks = !this.isWorks;
  }
  public changeTwitter() {
    this.isTwitter = !this.isTwitter;
  }
  public changeNote() {
    console.log(this.isNote);
    this.isNote = !this.isNote;
  }
}
</script>

<style lang="stylus" scoped>
.container {
    background-color: #6361A1;
    background-image: url('~assets/img/tarako_top.png');
    height: calc(100vh - 36px);

    .top_movie {
        position: absolute;
        top: 60px;
        right: 70px;
    }

    .top_music {
        position: absolute;
        top: 560px;
        right: 120px;
    }

    .top_works {
        position: absolute;
        bottom: 30px;
        left: 50%;
    }

    .top_twitter {
        position: absolute;
        bottom: 0px;
        left: 270px;
    }
    .top_note {
        position: absolute;
        top:40px;
        right: 70px;
    }

    .top_icons {
        position: absolute;
        top: 60px;
        left: 10px;
    }
}
</style>
