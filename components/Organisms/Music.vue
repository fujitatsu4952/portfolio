<template>
    <div class="music_container">
        <div class="music_title_container">
            <div class="music_delete" @click="click">×</div>

            <div class="music_title">TARAKO MUSIC</div>
        </div>
        <div class="music">
            <div class="box">
                <div class="wave -one"></div>
                <div class="wave -two"></div>
                <div class="wave -three"></div>
                <div class="title">
                    <audio src="~assets/music/goodTime.mp3" controls></audio>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue, Emit } from "nuxt-property-decorator";

@Component({
    components: {},
})
export default class start extends Vue {
    @Emit("click") public click() {}
}
</script>

<style lang="stylus" scoped>
.music_container {
    width: 300px;
    border: 10px solid rgb(255, 201, 201);
}

.music_title_container {
    background-color: rgb(255, 201, 201);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0px 0 5px;

    .music_delete {
        cursor: pointer;
        background-color: rgb(216, 215, 231);
        margin: 0 0px 0 10px;
        width: 30px;
        text-align: center;
        border-radius: 50%;
    }

    .music_title {
        font-weight: 600;
        font-size: 12px;
        padding: 0 20px 0 0;
    }
}

.music {
    display: flex;
    justify-content: center;
    align-items: center;
}

.box {
    width: 330px;
    height: 250px;
    box-shadow: 0 2px 30px rgba(black, 0.2);
    background: lighten(#f0f4c3, 10%);
    position: relative;
    overflow: hidden;
    transform: translate3d(0, 0, 0);
}

.wave {
    opacity: 0.4;
    position: absolute;
    top: 3%;
    left: 50%;
    background: #0af;
    width: 500px;
    height: 500px;
    margin-left: -250px;
    margin-top: -250px;
    transform-origin: 50% 48%;
    border-radius: 43%;
    animation: drift 3000ms infinite linear;
}

.wave.-three {
    animation: drift 5000ms infinite linear;
}

.wave.-two {
    animation: drift 7000ms infinite linear;
    opacity: 0.1;
    background: yellow;
}

.box:after {
    content: '';
    display: block;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(to bottom, rgba(#e8a, 1), rgba(#def, 0) 80%, rgba(white, 0.5));
    z-index: 11;
    transform: translate3d(0, 0, 0);
}

.title {
    position: absolute;
    left: 0;
    top: 40px;
    width: 100%;
    z-index: 1;
    line-height: 300px;
    text-align: center;
    transform: translate3d(0, 0, 0);
    color: white;
    text-transform: uppercase;
    font-family: 'Playfair Display', serif;
    letter-spacing: 0.4em;
    font-size: 24px;
    text-shadow: 0 1px 0 rgba(black, 0.1);
    text-indent: 0.3em;
}

@keyframes drift {
    from {
        transform: rotate(0deg);
    }

    from {
        transform: rotate(360deg);
    }
}
</style>
