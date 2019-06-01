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
     },
     bgColor: {
         type: String
     }
    },
    computed: {
      styleCustomCol() {
          return {
              flex: this.span ? this.span : '1',
              flexWrap: 'wrap',
              backgroundColor: this.bgColor,
              padding: '20px'
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