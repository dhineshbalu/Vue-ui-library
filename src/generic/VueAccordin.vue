<template>
  <div class="panel">
    <slot></slot>
  </div>
</template>
<script>
export default {
    name: 'VueAccordin',
    components: {

    },
    data() {
        return {
          selectedPanel: '',
        }
    },
    computed: {

    },
    methods: {
    },
    mounted() {
    }
}

</script>
<style scoped>
 .panel {
   max-width: 25%;
   max-height: 50%;
   text-align: center;
   border-radius: 5%;
 }
</style>