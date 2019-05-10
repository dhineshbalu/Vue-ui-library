<template>
<div>
    <div class="tags">
         <VueTag v-for="(tag,index) in list" :key="index" :index="index" @click="close">
              {{tag}}
         </VueTag>
         <VueInput class="input" id="name" type="text" :width="width" v-model="model.tag" :syncvalue="model.tag" ></VueInput>    
          <VueButton :color="'black'"  class="button" type="positive" size="xsmall" @click="add">ADD</VueButton>
    </div>
</div>
</template>
<script>
import VueTag from './VueTag'
import VueInput from './VueInput'
import VueButton from './VueButton'
export default {
    name:'VueTags',
    props: {
      list: {
          type: Array
      }
    },
    components: {
      VueTag,
      VueInput,
      VueButton
    },
    data() {
        return {
           width:150,
           model: {
               tag: 'tag'
           }
        }
    },
    methods: {
      close(val) {
          this.$emit('close',val)
      },
      add() {
          this.$emit('add',this.model.tag)
          this.model.tag = ''
      }
    },
    mounted() {

    }
}
</script>
<style scoped>
 .tags {
      max-width: 50%;
      max-height: 500px;
      background-color: lightgray;
      border: 2px solid black;
      padding:10px;
 }
 .input {
     display: inline-block;
 }
 .button {
     margin-left: 25px;
     cursor: pointer;
     font-weight: bold;
 }
</style>
