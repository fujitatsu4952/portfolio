<template>
    <div class="works">
        <div class="works_title_container">
            <div class="works_delete" @click="click">×</div>
            <div class="works_sub">※ここから本当に予約できるよ</div>
            <div class="works_title">TARAKO WORK</div>
        </div>
        <iframe class="chillnn" :src="chillnn" frameborder="0" allowfullscreen></iframe>
    </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue, Emit } from "nuxt-property-decorator";

@Component({
    components: {},
})
export default class Works extends Vue {
    @Emit("click") public click() {}
    public get chillnn() {
        return "https://www.chillnn.com/";
    }
}
</script>

<style lang="stylus" scoped>
.works {
    width: 375px;
    border: 10px solid rgb(255, 201, 201);

    .works_title_container {
        background-color: rgb(255, 201, 201);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 0 5px;

        .works_delete {
            cursor: pointer;
            background-color: rgb(216, 215, 231);
            margin: 0 0px 0 10px;
            width: 30px;
            text-align: center;
            border-radius: 50%;
        }

        .works_sub {
            font-size: 12px;
        }

        .works_title {
            font-weight: 600;
            font-size: 12px;
            padding: 0 20px 0 0;
        }
    }

    .chillnn {
        width: 375px;
        height: 700px;
        background-color: #ffffff;
    }
}
</style>
