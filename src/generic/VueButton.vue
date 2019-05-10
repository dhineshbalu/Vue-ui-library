<template>
        <button :style="setStyle" :class="setClass" @click="emitEvent"><slot></slot></button> 
</template>
<script>
export default {
    name: 'VueButton',
    props: {
     type: {
         type: String,
         default: 'default'
     },
     size: {
         type: String,
         default: 'small'
     },
     disable: {
         type: Boolean,
         default: false
     },
     color: {
         type: String,
     }
    },
    computed: {
       setClass() {
          return [
              this.type,
              this.size,
              this.disable ? 'disable' : ''
          ]
       },
       setStyle() {
           return {
               'backgroundColor': this.color
           }
       }
    },
    methods: {
        emitEvent() {
            this.$emit('click')
        }
    }
}
</script>
<style scoped>
 .primary {
    background-color: #6994db;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
.primary:hover {
    background-color: #3770ce;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
 .positive {
    background-color: #8fd16e;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
.positive:hover {
    background-color: #62bc56;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
 .negative {
    background-color: #e27c6c;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
.negative:hover {
    background-color: #e25944;
    color: white;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
 .default {
    color: black;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
.default:hover {
    color: black;
    padding:10px;
    font-size: 15px;
    font-weight: bold;
    border-radius: 5%;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis
}
.xsmall {
    width:100px;
}
.small {
   width: 150px
}
.medium {
  width: 200px
}
.large {
    width: 250px
}
.disable {
    cursor: not-allowed;
    background-color: lightgray;
    pointer-events: none;
}
</style>