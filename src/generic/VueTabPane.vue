<template>
      <div v-show="show">
          <slot></slot>
      </div>
</template>
<script>
 export default {
     name:'VueTabPane',
     props: {
       id: {
           type: String
       },
       name: {
           type: String
       }
     },
     data() {
         return {
             show: false
         }
     },
     computed: {

     },
     methods: {

     },
     mounted() {

     },
     watch: {
          '$parent.selectedTab'(n,o) {
             if( n == this.id) {
                 this.show = true
             } else {
                 this.show = false
             }
          }
     }
 }
</script>