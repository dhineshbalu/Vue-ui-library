<template>
   <div>
          <VueButton type="default" size="small" disable @click="buttonMethod">Button</VueButton>
          <VueButton type="primary" size="large" @click="buttonMethod">Button</VueButton>
          <VueButton type="positive" size="medium" @click="buttonMethod">Button</VueButton>
          <VueButton type="negative" @click="buttonMethod">Button</VueButton>
    </div>
</template>
<script>
import VueButton from '../generic/VueButton'
export default {
    name: 'VueButtonT',
    props: {

    },
    created() {

    },
    components: {
       VueButton
    },
    computed: {

    },
    methods: {
       buttonMethod() {
           console.log("button clicked")
       }
    },
    watch: {

    }
}
</script>
