<template>
     <div>
           <VueCards :color="color">
                   <div slot="head">
                       Title
                    </div>
                    <div slot="body"> 
                        Veronika Ossi Is a living in New York WuMeiShi, her favorite cat, music and the party. 
                        have a variety of shapes and sizes. Some puppies look adorable stay because make love, pity others because of short of stature. There are even some people who can be stupid because of their huge body shapes.
                     </div>
                     <div slot="footer">
                         Footer
                     </div>
            </VueCards>
      </div>
</template>
<script>
import VueCards from '../generic/VueCards'
export default {
    name: 'VueCardsT',
    props: {

    },
    created() {

    },
    components: {
       VueCards
    },
    data() {
      return {
          color: 'green'
      }
    },
    computed: {

    },
    methods: {

    },
    watch: {

    }
}
</script>
<style>

</style>