<template>
 <div>
    
    <div v-for="(item,index) in category" :key="index">
        <div>
            <div><img src="item." alt=""></div>
        </div>
    </div>

 </div>
</template>

<script>
 export default {
   name: '',
   props: {
     category:{
       type:Array
     }
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {

   },
   mounted() {

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>