<template>
<div>

    <div class="top df h50 ">

        <div class="goback ccc " @click="goback">
            <van-icon name="arrow-left" />
        </div>

        <div class="ccc fs18 w300 text2">最近浏览</div>

    </div>

    <div>

          <div>
            <div v-for="(item,index) in arr" :key="index" class="x_box_container">

                <van-card :price="item.present_price" :title="item.name" :thumb="item.image_path" />
                <div>
                    <div @click="del(item,index)" class="x_box ccc">
                        <van-icon name="cross" />
                    </div>
                </div>
            </div>
        </div>

    </div>

</div>
</template>

<script>
import uniq from 'lodash/uniq'
export default {
    name: '',
    props: {},
    components: {

    },
    data() {
        return {
            getDatas: null,
            arr:[]

        }
    },
    methods: {
        getData() {
            this.getDatas = JSON.parse(localStorage.getItem('viewss'))
            console.log(this.getDatas);
            this.getDatas = uniq(this.getDatas)
            this.arr = []
            this.getDatas.map((item, index) => {
                this.$api.getGoodsOne(item).then(res => {
                    this.arr.push(res.goods.goodsOne)
                    console.log(res);
                }).catch(err => {
                    console.log(err);
                })
            })
            
        },
        goback() {
            this.$router.back()
        }

    },
    mounted() {
        this.getData()
       

    },
    watch: {

    },
    computed: {

    }
}
</script>

<style lang="scss" scoped>
.top {
    border-bottom: 1px solid rgb(180, 176, 176);
}

.text1 {
    width: 40px;
}

.goback {
    width: 30px;
}

.text2 {
    letter-spacing: 2px;
}
</style>
