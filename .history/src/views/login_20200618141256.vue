<template>
 <div class="box df f-column">
    <div class="goback b1"><van-icon name="arrow-left" /></div>
    <div class="df">

        
    
    </div>
 </div>
</template>

<script>
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
.box{
    width: 100%;
    height: 200px;
    background: url('../assets/login.jpg');
    .goback{
        width: 36px;
        height: 36px;
        font-size:20px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        background-color: #c6cfcc;
        position: relative;
        left: 10px;
        top: 10px;
    }
}
</style>