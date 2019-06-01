<template>
 <div>
    <VueSwitch id="switch" v-model="switchValue" :disabled="false" :checked="true" on="val on.." off="val off.." @input="outputValue"></VueSwitch>
 </div>
</template>
<script>
export default {
    name: 'VueSwitchT',
    data() {
      return {
          switchValue: ''
      }
    },
    methods: {
      outputValue() {
        console.log(this.switchValue)
      }
    },
    mounted() {
      this.$events.emit('gc:switch', {
          id: 'switch',
          task: 'control|checked',
          data:  false
      })
    }
}
</script>
<style>

</style>