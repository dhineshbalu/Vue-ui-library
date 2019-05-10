<template>
   <div class="tag">
       <slot></slot>
       <span class="close" @click="close">&times;</span>
    </div>
</template>
<script>
export default {
    name:'VueTag',
    props: {
       index: {
              type: Number
          }
    },
    components: {
        
    },
    data() {
        return {

        }
    },
    computed: {

    },
    methods: {
      close() {
          this.$emit('click',this.index)
      }
    },
    mounted() {
        
    }
}
</script>
<style scoped>
  .tag {
      max-width: 300px;
      max-height: 150px;
      display: inline-block;
      background-color: black;
      color:white;
      padding:15px;
      margin:5px;
      border-radius: 5%;
      letter-spacing: 1px;
      word-spacing: 2px;
      font-weight: bold;
      vertical-align: center;
  }
  .close {
  color: white;
  float: right;
  font-size: 25px;
  font-weight: bold;
  cursor: pointer;
  margin-left:10px;
}
</style>
