<template>
 <div>

 </div>
</template>

<script>
import axios from 'axios'
 export default {
   name: '',
   props: {
   },
   components: {

   },
   data () {
     return {
       citys:[],
     }
   },
   methods: {
     
   },
   mounted() {
     axios.get('./city.json').then(res=>{
      this.citys
     }).catch(err=>{
       console.log(err)
     })
   },
   watch: {

   },
   computed: {

   }
 }
</script>

<style scoped lang='scss'>

</style>