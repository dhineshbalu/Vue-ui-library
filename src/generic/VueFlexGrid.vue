<template>
<div :style="customFlexBox">
    <slot></slot>
</div>
</template>
<script>
import VueFlexCol from './VueFlexCol'
export default {
    name: 'VueFlexGrid',
    components: {
      VueFlexCol
    },
    computed: {
     customFlexBox() {
         return {
             display: 'Flex',
             maxHeight: '100%'   
         }
     }
    },
    methods: {

    },
    mounted() {

    },
    watch: {

    }
}
</script>
<style>
</style>