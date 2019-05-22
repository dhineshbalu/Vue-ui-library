<template>
<div :style="styleCustomCol">
     <slot></slot>
</div>
</template>
<script>
export default {
    name: 'VueFlexCol',
    props: {
     span: {
         type: String
     }
    },
    computed: {
      styleCustomCol() {
          return {
              flex: this.span ? this.span : '1',
              flexWrap: 'wrap'
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
.span1_col3 {
}
</style>