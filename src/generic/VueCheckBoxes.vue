<template>
 <div :id="id" class="containers">
    <slot></slot>
 </div>
</template>
<script>
export default {
    name: 'VueCheckBoxes',
    props: {
      id: {
          type: String
      }
    },
    data() {
       return {
           lists: [],
           selected: []
       }
    },
    computed: {

    },
    methods: {

    },
    mounted() {
        let list = []
      for (var i=0;i<this.$children.length;i++) {
         list.push({
             index: i,
             label: this.$children[i].label,
             value: this.$children[i].value
         })
      }
      this.lists = list
      this.$events.on('gc:checkBox',(o)=> {
          if (!_.intersection(this.selected,[o.value]).length) {
            this.selected.push(o.value)
          } else {
              this.selected = _.without(this.selected,o.value)
          }
          this.$emit('input',this.selected)
      })
    }
}
</script>
<style>
 .containers {
     max-width: 1000px;
 }
</style>