<template>
<div>

    <div class="top df h50 ">

        <div class="goback ccc " @click="goback">
            <van-icon name="arrow-left" />
        </div>

         <div class="ccc fs18 w300 text2">我的收藏</div>

    </div>

    <div>
        <div>
            <div></div>
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
      goback(){
        this.$router.back()
      },
      getCollectionList(){
        this.$api.getCollectionList().then(res=>{
          console.log(res);
        }).catch(
          err=>{}
        )
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

.top {
    border-bottom: 1px solid rgb(180, 176, 176);
}

.text1 {
    width: 40px;
}
.goback{
  width: 30px;
}
</style>
