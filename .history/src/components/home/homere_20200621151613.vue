<template>
<div>
    <div class="w375 recom" >
        <div class="df m-l-20  a-center  h36">商品推荐</div>
    </div>
    <div class="container" ref="container">
        <div class="box">
              <div v-for="(item,index) in recommend" :key="i">

              
              </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: '',
    props: {
      recommend:{
        type: Array
      }
    },
    components: {

    },
    data() {
        return {

        }
    },
    methods: {

    },
    mounted() {
console.log(this.recommend);
    },
    watch: {

    },
    computed: {

    }
}
</script>

<style scoped lang='scss'>
.recom{
  border-bottom:1px solid #F0F0EE;
}
</style>
