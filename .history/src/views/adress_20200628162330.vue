<template>
<div>
    <div class="top df  h50">
        <div class="ccc text1">
            <div @click="goback">
                <van-icon name="arrow-left" />
            </div>
        </div>

        <div class="ccc w300 text2 ">地址列表</div>

    </div>

    <div>

        <div class="noGood">暂无收货地址~~</div>

    </div>

    <div>

        <van-address-list v-model="chosenAddressId" :list="list" :disabled-list="disabledList" disabled-text="以下地址超出配送范围" default-tag-text="默认" @add="onAdd" @edit="onEdit" />

    </div>

</div>
</template>

<script>
import { Toast } from 'vant';
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
        },

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
.top {
    border-bottom: 1px solid rgb(180, 176, 176);
}

.text1 {
    width: 40px;
}

.text2 {
    color: rgb(116, 87, 87);
    font-weight: 700;
}

.noGood {
    color: gray;
    font-size: 20px;
}
</style>
