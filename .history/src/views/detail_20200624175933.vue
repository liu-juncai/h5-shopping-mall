<template>
 <div>
       this is detail 
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
            id:'',
     }
   },
   methods: {

   },
   mounted() {
       this.id = this.$route.query.id 
       cl

   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>