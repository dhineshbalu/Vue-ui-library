<template>
  <div class="spanel">
       <h2 @click="selectPanel" class="headClass">{{name}}</h2>
       <div v-show="visible" class="bodyClass">
         <slot></slot>
       </div>
  </div>
</template>
<script>
export default {
    name: 'VueAccordinPanel',
    props: {
     name: {
       type: String
     }
    },
    components: {

    },
    data() {
        return {
          visible: false
        }
    },
    computed: {
         bodyClass() {

         }
    },
    methods: {
       selectPanel() {
          if( this.$parent.selectedPanel == this.name) 
            this.$parent.selectedPanel = ''
         else 
            this.$parent.selectedPanel = this.name
       }
    },
    mounted() {

    },
    watch: {
      '$parent.selectedPanel'(n,o) {
        if (this.name == n) {
          this.visible = true
        } else {
          this.visible = false
        }
      }
    }
}

</script>
<style scoped>
  .headClass {
    cursor: pointer;
    padding:5px;
    font-weight: bold;
    letter-spacing: 1px;
    word-spacing: 2px;
    background-color: black;
    color:white;
    transition: all 1.5s ease;
  }
   .headClass:hover {
    background-color: white;
    color:black;
  }
  .bodyClass {
    padding:5px;
    letter-spacing: 1px;
    word-spacing: 2px;
    word-break: break-all;
  }
  .spanel {
    max-height: 400px;
  }
</style>