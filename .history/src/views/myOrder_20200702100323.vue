<template>
<div>
    <div class="top df h50">
        <div class="ccc text1">
            <div @click="goback">
                <van-icon name="arrow-left" />
            </div>
        </div>

        <div class="ccc w300 text2">我的订单</div>
    </div>

    <div>
        <van-tabs v-model="active" @click="onClick">

            <van-tab title="全部" class="ccc m-t-20">
                开发中,敬请期待..
            </van-tab>
            <van-tab title="待支付" class="ccc m-t-20"> 开发中,敬请期待..</van-tab>
            <van-tab title="代发货" class="ccc m-t-20"> 开发中,敬请期待..</van-tab>
            <van-tab title="待收货" class="ccc m-t-20">
                开发中,敬请期待..
            </van-tab>

            <van-tab title="已完成" class="j-center">

                <div class="  loop_item_box df f-column a-center">

                    <div class="loop_item " v-for="(item,index) in list" :key="index">

                        <div class=" m-t-8">
                            <div>订单编号:{{item.order_id}}</div>
                        </div>
                        <div class="line_box m-t-20  j-center">
                            <div class="line"></div>
                        </div>

                        <div class="all m-t-15">
                            <div v-for="(item1,index1) in item.order_list" :key="index1">
                                <van-card :num="item1.count" :price="item1.mallPrice" :title="item1.name" :thumb="item1.image_path" />
                            </div>
                        </div>
                        <div class="line_box m-b-10 j-center">
                            <div class="line"></div>
                        </div>

                        <div class="df fs14 f-column ">

                            <div>创建时间:{{item.add_time}}</div>
                            <div>收货地址:{{item.address}}</div>
                            <div>共{{item.order_list.length}}件商品 合计:{{item.order_list[0].count*item.mallPrice}}:00元</div>

                        </div>
                    </div>
                </div>

            </van-tab>

        </van-tabs>
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
            active: 0,
            list: [],

        }
    },
    methods: {
        goback() {
            this.$router.back()
        },
        onClick(name, title) {

        },
        getMyOrder() {

            this.$api.getMyOrder().then(res => {
                this.list = res.list
                console.log(this.list);
            }).catch(err => {
                console.log(err);
            })

        },
        fn(){
            this.active = this.$route.quert
        }

    },
    mounted() {

        this.getMyOrder()

    },
    watch: {

    },
    computed: {

    }
}
</script>

<style lang="scss" scoped>
.line_box {}

.line {
    width: 100%;
    height: 1px;
    background: rgb(170, 163, 163);
}

.all .van-card {
    background: white !important;
}

.loop_item_box {

    margin-left: 10px;
    margin-right: 10px;

}

.loop_item {

    margin-top: 20px;
    background: white;
    border-radius: 10px;
    padding: 20px 10px 16px 10px;

}

.van-tab__pane {
    background: rgb(239, 240, 243);

}

.all {
    width: 320px;
    border-radius: 100px;

}

.text1 {
    width: 40px;
}

.text2 {
    color: rgb(116, 87, 87);
    font-weight: 700;
}

/deep/.van-tab {

    flex-basis: 20% !important;
}
</style>
