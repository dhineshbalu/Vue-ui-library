<template>
   <option :value="value" :disabled="disable" class="optionStyle" :selected="defaultSetting">
     <slot></slot>
   </option>
</template>
<script>
export default {
    name: 'VueOption',
    props: {
        value: {
            type: String
        },
        disable: {
            type: Boolean,
            default: false
        },
        default: {
            type: String
        }
    },
    computed: {
        defaultSetting() {
            return this.value == this.default
        }
    }
}
</script>
<style>
 .optionStyle {
      position: absolute;
      cursor: pointer;
      padding: 10px;
      font-size: 15px;
      font-weight: bold;
      letter-spacing: 1px;
      word-spacing: 1px;
      width:inherit;
      height: inherit;
     border: 1px solid black;
 }
</style>