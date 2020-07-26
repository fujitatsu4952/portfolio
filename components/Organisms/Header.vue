<template>
  <div class="header">
    <img class="header_logo" src="~assets/img/tarako.png" />
    <div class="header_news">
      <span>
        ☀︎1998年7月16日生まれ。横浜育ち。今は大阪に住みながら東大生やってます。月に一回くらい、どうしてもラッパーになりたい日が来ちゃってて、それを「男の子の日」と呼んでいます　★最近はサマータイムを導入して7時から活動するようにしたらすこぶる
        調子が良い。とりあえず、運動してぇ。
      </span>
    </div>
    <div class="header_date">
      {{ getDate }}
    </div>
  </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue } from "nuxt-property-decorator";
import dayjs from "dayjs";

@Component({
  components: {}
})
export default class Header extends Vue {
  public get getDate() {
    return dayjs().format("YYYY/MM/DD");
  }
}
</script>

<style lang="stylus" scoped>
.header {
    width: 100%;
    height: 36px;
    background-color: rgb(255, 201, 201);
    display: flex;
    .header_logo {
        padding:8px 0 8px 10px;
        width:10%;
        height: 20px;
    }
    .header_news {
        overflow: hidden;
        position: relative;
        height: 20px;
        margin: 4px 0 4px 10px;
        padding:4px 0;
        color: #FFB400;
        font-size: 14px;
        font-weight: bold;
        background: #333333;
    }
    .header_news:after{
        content: ' ';
        display: block;
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        background-image: linear-gradient(#0a0600 1px, transparent 0px), linear-gradient(0, #0a0600 1px, transparent 1px);
        background-image: -webkit-linear-gradient(#0a0600 1px, transparent 0px), -webkit-linear-gradient(0, #0a0600 1px, transparent 1px);
        background-size: 2px 2px;
        z-index: 10;
    }
    .header_news span {
        display: inline-block;
        white-space: nowrap;
        padding-left: 100%;
        -webkit-animation-name: marquee;
        -webkit-animation-timing-function: linear;
        -webkit-animation-iteration-count: infinite;
        -webkit-animation-duration: 15s;
        -moz-animation-name: marquee;
        -moz-animation-timing-function: linear;
        -moz-animation-iteration-count: infinite;
        -moz-animation-duration: 15s;
        animation-name: marquee;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
        animation-duration: 15s;
    }
    @-webkit-keyframes marquee {
    from   { -webkit-transform: translate(0%);}
    99%,to { -webkit-transform: translate(-100%);}
    }
    @-moz-keyframes marquee {
    from   { -moz-transform: translate(0%);}
    99%,to { -moz-transform: translate(-100%);}
    }
    @keyframes marquee {
    from   { transform: translate(0%);}
    99%,to { transform: translate(-100%);}
    }
    .header_date {
        padding:8px 0;
        width: 300px;
        text-align: center;
        font-size: 14px;
        // border-left: 1px solid;
    }
}
</style>
