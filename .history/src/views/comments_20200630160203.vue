<template>
<div>
    <div class="top df h50">
        <div class="ccc text1">
            <div @click="goback">
                <van-icon name="arrow-left" />
            </div>
        </div>

        <div class="ccc w300 text2">评价中心</div>
    </div>

    <div>
        <div class="pic_box">
            <img src="../assets/evaluate.jpg" alt="">
        </div>
        <div>

            <div class="df">
                <div class="f1 b1">待评价</div>
                <div class="f1 b1">已评价</div>
            </div>

        </div>
    </div>

</div>
</template>

<script>
export default {
    name: '',
    props: {},
    components: {

    },
    data() {
        return {

        }
    },
    methods: {
        goback() {
            history.go(-1)
        }

    },
    mounted() {

    },
    watch: {

    },
    computed: {

    }
}
</script>

<style lang="scss" scoped>
.pic_box {
    width: 375px;
}

.pic_box img {
    width: 100%;
}

.top {
    border-bottom: 1px solid rgb(180, 176, 176);
}
</style>
