<template>
<div class="df b1">

    <div v-for="(item,index) in category" :key="index">
        
            <div>
                <img class="pic" :src="item.image" alt="">
            </div>
            <div>
                {{item.mallCategoryName}}
            </div>
        
    </div>

</div>
</template>

<script>
export default {
    name: '',
    props: {
        category: {
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

    },
    watch: {

    },
    computed: {

    }
}
</script>

<style scoped lang='scss'>
.pic{
  width: 50px;
  height: 50px;
}
</style>
