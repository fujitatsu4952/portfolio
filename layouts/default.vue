<template>
  <div class="layout">
    <top-header />
    <Nuxt />
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";
import TopHeader from "@/components/Organisms/Header.vue";

@Component({
  components: {
    TopHeader
  },
  head: {
    bodyAttrs: {
      class: "body-class"
    }
  }
})
export default class defaultLayout extends Vue {}
</script>

<style lang="stylus" scoped>
.body-class {
  margin: 8px;
}
.layout {
    min-height: 100vh;
    width: 100vw;
    padding: 0;
    margin: 0;
}
</style>
