<template>
<div>
    <div class="top df h50">
        <div class="ccc text1">
            <div @click="goback">
                <van-icon name="arrow-left" />
            </div>
        </div>

        <div class="ccc w300 text2">地址列表</div>
    </div>

    <div>
        <van-address-edit :area-list="areas" :address-info="AddressInfo" show-delete show-set-default show-search-result :search-result="searchResult" :area-columns-placeholder="['请选择', '请选择', '请选择']" @save="onSave" @delete="onDelete" @change-detail="onChangeDetail" />
    </div>
</div>
</template>

<script>
import {
    Toast
} from "vant";
import area from "./lib/area.js";
export default {
    name: "",
    props: {},
    components: {},
    data() {
        return {
            areas: area,
            searchResult: [],
            list: [],
            list1: [],
            AddressInfo: {},
            id: "",
            onelist:[]
            

        };
    },
    methods: {

        goback() {
            history.go(-1);
        },

        onSave(content) {

            console.log(content);

            this.$api
                .getIncreaseAddress(
                    content.name,
                    content.tel,
                    content.address,
                    content.isDefault,
                    content.province,
                    content.city,
                    content.county,
                    content.addressDetail,
                    content.areaCode,
                    content.id
                )
                .then(res => {
                    this.$router.push({
                        name: "adress"
                    });
                })
                .catch(err => {
                    console.log(err);
                });

        },
        onDelete(id) {

            this.$api.getDeleteAddress(id).then(res => {
                console.log(res);
            }).catch(err => {
                console.log(err);
            })

        },
        onChangeDetail(val) {
            if (val) {
                this.searchResult = [{
                    name: "东方广场",
                    address: "成都市"
                }];
            } else {
                this.searchResult = [];
            }
        },
        fn() {
            if (this.$route.params.oneList) {
                this.list = JSON.parse(this.$route.params.oneList)
            }
        }

    },
    mounted() {
        this.fn()

        this.onelist = JSON.parse(this.$route.params.oneList)

    },
    watch: {},
    computed: {}
};
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
</style>
