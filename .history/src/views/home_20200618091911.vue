<template>
 <div>

    <div class="container">
      <div class="box">
      </div>
    </div>

 </div>
</template>

<script>
import axios from "axios"
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {

     }
   },
   methods: {
// getRecommend(){
// this.$api.getRecommend().then(res=>{
//         console.log(11);
//         console.log(res);
//       }).catch(err=>{
//         console.log(err);
//       })
// }
   },
   mounted() {
      // this.getRecommend()
      
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>
.one{
  width:100px;
  height:100px;
  border:1px solid red;
}
</style>