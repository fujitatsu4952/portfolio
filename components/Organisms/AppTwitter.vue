<template>
  <div class="twitter">
    <div class="twitter_title_container">
      <div class="twitter_delete" @click="click">×</div>
      <div class="twitter_title">Djたらこ|fujii tatsuya</div>
    </div>
    <div class="twitter-widget" style="width:373px;">
      <v-timeline
        :id="twitterId"
        :source-type="'profile'"
        :options="{ height: twitterHeight }"
      />
    </div>

    <!-- <iframe class="twitter" href="https://twitter.com/fujitatsu49?ref_src=twsrc%5Etfw" :src="twitter" frameborder="0" allowfullscreen></iframe> -->
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
export default class AppTwitter extends Vue {
  public twitterId: string = "fujitatsu49";
  public get twitterHeight() {
    return "506px";
  }
  @Emit("click") public click() {}
  public get twitter() {
    return "https://twitter.com/fujitatsu49?ref_src=twsrc%5Etfw”";
  }
}
</script>

<style lang="stylus" scoped>
.twitter {
    width: 370px;
    height: 534px;
    border: 10px solid rgb(255, 201, 201);

    .twitter_title_container {
        background-color: rgb(255, 201, 201);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 0 5px;

        .twitter_delete {
            cursor: pointer;
            background-color: rgb(216, 215, 231);
            margin: 0 0px 0 10px;
            width: 30px;
            text-align: center;
            border-radius: 50%;
        }

        .twitter_title {
            font-weight: 600;
            font-size: 12px;
            padding: 0 20px 0 0;
        }
    }

    .twitter {
        width: 360px;
        height: 500px;
        background-color: #ffffff;
    }
}
</style>
