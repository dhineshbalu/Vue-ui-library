<template>
   <div>
       <VueTags :list="list" @close="remove" @add="addList">

       </VueTags>
    </div>
</template>
<script>
import VueTags from '../generic/VueTags'
export default {
    name:'VueTagsT',
    components: {
      VueTags
    },
    data() {
        return {
           list: ['tag1','tag2','tag3','tag1','tag2','tag3']
        }
    },
    computed: {

    },
    methods: {
     remove(index) {
         this.list.splice(index,1)
     },
     addList(val) {
         this.list.push(val)
     }
    },
    mounted() {
        
    }
}
</script>
<style>

</style>
