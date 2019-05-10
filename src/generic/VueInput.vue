<template>
     <div>
         <input :id="id" :style ="userStyle" :class="userClass" :type="type"  :value="model"  @input="userInput($event.target.value)"/>
      </div>
</template>
<script>
export default {
    name: 'VueInput',
    props: {
      id: {
        type: String
      },
      syncvalue: {
          type: String,
      },
      width: {
          type: Number,
          default: 150
      },
      type: {
          type: String,
          default: 'text'
      }
    },
    data() {
     return {
         model: ''
     }
    },
    computed: {
         userClass() {
             return [
                 'input'
             ]
         },
         userStyle() {
             return {
                  width: this.width + 'px'
             }
         }
    },
    methods: {
      userInput(v) {
          this.model = v
          this.$emit('input',this.model)
      }
    },
    mounted() {
      this.model = this.syncvalue
    },
    watch: {
      'model'(n,o) {
          if( this.model != n)
          this.model = n
      }
    }
}
</script>
<style scoped>
  .input {
      padding:10px;
      width:150px;
      border-bottom: 2px solid lightgray;
      border-left-width: 0px;
      border-right-width: 0px;
      border-top-width: 0px;
      font-size: 15px;
      letter-spacing: 1px;
      word-spacing: 2px;
      font-weight: bold;
      transition: border 1s ease;
      outline: none;
  }
   .input:focus {
      padding:10px;
      width:150px;
       border-bottom: 2px solid black;
      border-left-width: 0px;
      border-right-width: 0px;
      border-top-width: 0px;
      font-size: 15px;
      letter-spacing: 1px;
      word-spacing: 2px;
      font-weight: bold;
      outline: none;
  }
</style>
