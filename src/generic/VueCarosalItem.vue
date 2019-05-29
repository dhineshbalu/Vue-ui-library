<template>
 <div :id="id" v-show="active">
   <slot> </slot>
 </div>
</template>
<script>
export default {
    name: 'VueCarosalItem',
    props: {
      id: {
          type: String
      }
    },
    data() {
      return {
          active: false
      }
    },
    computed: {

    },
    methods: {

    },
    mounted() {

    },
    watch: {
        '$parent.selected' (n,o) {
            if (this.id == n) {
                this.active = true
            } else {
                this.active = false
            }
        }
    }
}
</script>
<style>

</style>