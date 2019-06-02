<template>
   <div>
        <component :is="active"></component>
        <!-- <h2>
            The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.The opacity property sets the opacity level for an element.

The opacity-level describes the transparency-level, where 1 is not transparent at all, 0.5 is 50% see-through, and 0 is completely transparent.
        </h2> -->
        <!-- <VueButton type="negative" @click="activate">Show Component</VueButton> -->
         <!-- <button @click="emitLoad">Show</button>
        <button @click="offLoad">Hide</button> -->
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
import VueGridTest from './VueGridTest'
import VueSelectT from './VueSelectT'
import VueCarosalT from './VueCarosalT'
import VueMessagingT from './VueMessagingT'
import VueSwitchT from './VueSwitchT'
import VueCheckBoxT from './VueCheckBoxT'
import VueRadioT from './VueRadioT'
import Table from './Table.vue'
import VueDropDownT from './VueDropDownT'
export default {
    name: 'LandingPage',
    props: {

    },
    created() {

    },
    data() {
        return {
            active: VueDropDownT
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
       VueLoaderT,
       VueGridTest,
       VueSelectT,
       VueMessagingT,
       VueSwitchT,
       VueCheckBoxT,
       VueRadioT,
       Table,
       VueDropDownT
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
