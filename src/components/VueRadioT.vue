<template>
    <div>
        <VueRadios id="radioBox" v-model="selectedRadio" @input="outputValue" default="value2">
            <VueRadio v-for="(list,index) in values" :key="index" :name="list.value" :label="list.label"></VueRadio>
        </VueRadios>
    </div>
</template>
<script>
 export default {
     name: 'VueRadioT',
     props: {
         
     },
     data() {
      return {
        selectedRadio: '',
        values: [{
            label: 'label1',
            value: 'value1'
        }, 
        {
            label: 'label2',
            value: 'value2'
        }]
      }
     },
     computed: {

     },
     methods: {
       outputValue() {
           console.log(this.selectedRadio)
       }
     },
     mounted() {

     }
 }
</script>
<style>

</style>