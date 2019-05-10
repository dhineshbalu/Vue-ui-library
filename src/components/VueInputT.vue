<template>
    <div>
         <VueInput id="name" type="password" :width="width" v-model="model.username" :syncvalue="username" @input="validateName"></VueInput>
    </div>
</template>
<script>
import VueInput from '../generic/VueInput'
export default {
    name: 'VueInputT',
    components: {
     VueInput
    },
    data() {
        return {
            model: {
               username: ''
            },
            username: 'Dhinesh',
            width: 300
        }
    },
    methods: {
      validateName() {
         console.log(this.model.username)
      }
    }
}
</script>
<style>

</style>