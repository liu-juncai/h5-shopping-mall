<template>
<div>
    
    <div>
        <top></top>
    </div>
    

</div>
</template>

<script>

import top from '../components/home/top.vue'

export default {
    name: '',
    props: {},
    components: {
        top
    },
    data() {
        return {
          

        }
    },
    methods: {
        

    },
    mounted() {
    //   this.cityname =  this.$route.params.cityname
    //   console.log(this.cityname);
    },
    watch: {

    },
    computed: {

    }
}
</script>

<style lang="scss" scoped>
.top_left {

    background: #F0F0EE;
}
</style>
