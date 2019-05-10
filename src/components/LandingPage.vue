<template>
   <div>
        <component :is="active"></component>
        <!-- <VueButton type="negative" @click="activate">Show Component</VueButton> -->
         <button @click="emitLoad">Show</button>
        <button @click="offLoad">Hide</button>
  </div>
</template>
<script>
import VueButtonT from './VueButtonT'
import VueInputT from './VueInputT'
import VueTabT from './VueTabT'
import VueCardsT from './VueCardsT'
import VueModalFormT from './VueModalFormT'
import VueButton from '../generic/VueButton'
import VueTagsT from './VueTagsT'
import VuePanelT from './VuePanelT'
import VueLoaderT from './VueLoaderT'
export default {
    name: 'LandingPage',
    props: {

    },
    created() {

    },
    data() {
        return {
            active: VueLoaderT
        }
    },
    components: {
       VueButtonT,
       VueInputT,
       VueTabT,
       VueCardsT,
       VueModalFormT,
       VueButton,
       VueTagsT,
       VuePanelT,
       VueLoaderT
    },
    computed: {

    },
    methods: {
       buttonMethod() {
           console.log("button clicked")
       },
       activate() {
           this.active = VueModalFormT
       },
         emitLoad() {
            this.$events.emit('showLoad',true)
        },
        offLoad() {
            this.$events.emit('showLoad',false)            
        }
    },
    mounted() {
       this.$events.on('changeActive',() => {
           this.active = ''
       })
    },
    watch: {

    }
}
</script>
