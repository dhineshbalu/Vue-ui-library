<template>
  <select class="select" @change="selectedOption">
   <VueOption v-for="list in datas" :key="list.id" :value="list.value" :disable="list.disable" :default="defaultVal">{{list.label}}</VueOption>
 </select>
</template>
<script>
export  default {
    name: 'VueSelect',
    props: {
      id: {
          type: String
      },
      defaultVal: {
          type: String
      }
    },
    data() {
        return {
           datas: []
        }
    },
    computed: {

    },
    methods: {
      selectedOption(event) {
        this.$emit('input',event.target.value)
      }
    },
    mounted() {
      this.$events.on('gc:select',(o) => {
          if (this.id == o.id) {
              this.datas = o.data
          }
      })
    }
}
</script>
<style>
  .select {
      position: relative;
      cursor: pointer;
      padding: 5px;
      font-size: 15px;
      font-weight: bold;
      letter-spacing: 1px;
      word-spacing: 1px;
      min-width: 200px;
      max-width:800px;
      min-height:30px;
      max-width: 50px;
      border:2px solid black;
  }
</style>