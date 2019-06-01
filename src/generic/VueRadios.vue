<template>
    <div :id="id">
         <slot></slot>
    </div>
</template>
<script>
 export default {
     name: 'VueRadios',
     props: {
         id: {
             type: String
         },
         default: {
             type: String
         }
     },
     data() {
        return {
            checked: ''
        }
     },
     computed: {

     },
     methods: {

     },
     mounted() {
         this.checked = this.default
        this.$events.on('gc:radio', (o) => {
            this.$emit('input',o)
        })
     }
}

</script>
<style>

</style>