<template>
    <div class="television">
        <div class="television_title_container">
            <div class="television_delete" @click="click">×</div>

            <div class="television_title">TARAKO TV</div>
        </div>
        <video class="movie" src="~assets/movie/top.mp4" controls　autoplay playsinline />
    </div>
</template>

<script lang="ts">
import { Component, Vue, Emit } from "nuxt-property-decorator";

@Component({
    components: {},
})
export default class Television extends Vue {
    @Emit("click") public click() {}
}
</script>

<style lang="stylus" scoped>
.television {
    width: 500px;
    border: 10px solid rgb(255, 201, 201);

    .television_title_container {
        background-color: rgb(255, 201, 201);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 0 5px;

        .television_delete {
            cursor: pointer;
            background-color: rgb(216, 215, 231);
            margin: 0 0px 0 10px;
            width: 30px;
            text-align: center;
            border-radius: 50%;
        }

        .television_title {
            font-weight: 600;
            font-size: 12px;
            padding: 0 20px 0 0;
        }
    }
}

.movie {
    width: 500px;
}
</style>
