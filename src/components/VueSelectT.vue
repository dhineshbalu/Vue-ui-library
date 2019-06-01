<template>
       <VueSelect id="select1" v-model="selected" @input="selectedOption" defaultVal="option1"></VueSelect>
</template>
<script>
export  default {
    name: 'VueSelectT',
    data() {
        return {
          selected: '',
          data: [
              {
                  id: 'option1',
                  label: 'option1',
                  value: 'option1',
                  disable: true
              },
              {
                  id: 'option2',
                  label: 'option2',
                  value: 'option2'
              },
              {
                  id: 'option3',
                  label: 'option3',
                  value: 'option3'
              }
          ]
        }
    },
    computed: {

    },
    methods: {
      selectedOption() {
          console.log(this.selected)
      }
    },
    mounted() {
       this.$events.emit('gc:select',{
           id: 'select1',
           data: this.data
       })
    }
}
</script>
<style>

</style>