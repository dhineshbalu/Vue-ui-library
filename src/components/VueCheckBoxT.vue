<template>
    <div>
        <VueCheckBoxes id="checkBox1" v-model="selectedCheckBox" @input="outputValues">
          <VueCheckBox   @input="outputValues" v-for="(list,index) in values" :key="index" :val="list.value" :label="list.label" > </VueCheckBox>
        </VueCheckBoxes>
    </div>
</template>
<script>
export default {
    name: 'VueCheckBoxT',
    props: {

    },
    data() {
     return {
         selectedCheckBox: [],
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
     outputValues() {
         console.log(this.selectedCheckBox)
     }
    },
    mounted() {

    }
}
</script>
<style>

</style>