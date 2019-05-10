<template>
<div class="modalContainer">
   <div class="modalContent">
      <span class="close" @click="DontShow">&times;</span>
     <div class="modalHead">
        <slot name="head"></slot>
      </div>
      <div class="modalBody">
        <slot name="body"></slot>
      </div>
      <div class="modalFooter">
        <slot name="footer"></slot>
      </div>
   </div>
</div>
</template>
<script>
export default {
    name:'VueModalForm',
    data() {
        return {
          displayModal: true
        }
    },
    computed: {

    },
    methods: {
     DontShow() {
       this.$events.emit('close','')
     }
    },
    mounted() {
      this.displayModal = true
    }
}
</script>
<style scoped>
.modalContainer {
    z-index:1;
    position: fixed;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.4);
    overflow: scroll;
}
.modalContent {
  background-color: white;
  max-width:80%;
  max-height:100%;
  margin-left:10%;
  margin-top:5%;
  text-overflow: ellipsis;
}
.modalHead {
  background-color: #093884;
  color:white;
  font-weight: bold;
  letter-spacing: 1px;
  word-spacing: 2px;
  text-align: left;
  max-height: 150px;
  padding-top: 0.4px;
  border-bottom-left-radius: 10%;
  border-bottom-right-radius: 10%;
}
.modalBody {
  padding:15px;
  max-width: 100%;;
  max-height: 100%;
  background-color: white;
}
.modalFooter {
   max-width: 100%;
   max-height: 100%;
   background-color: white;
}
.close {
  color: white;
  float: right;
  font-size: 35px;
  font-weight: bold;
  cursor: pointer;
  margin-right: 10px;
}
</style>
