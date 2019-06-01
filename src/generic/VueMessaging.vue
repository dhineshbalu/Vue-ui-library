<template>
  <transition name="messageBox" mode="in-out">
      <div :id="id" :class="styleBox" :style="positionTop" >
          <span v-html="msgContent"></span>
          <span class="close" @click="closeBox">&times</span>
      </div>
  </transition>
</template>
<script>
export default {
    name: 'VueMessaging',
    props: {
      message: {
          type: Object
      },
      index: {
          type: Number
      }
    },
    data() {
        return {
          id: '',
          timeout: 0
        }
    },
    computed: {
        msgContent() {
          return `<strong>${this.message.data}</strong>`
       },
       styleBox() {
           return this.message.type
       },
       positionTop() {
           return {
               marginTop: `${this.index * 7}%`
           }
       },
       getIndex() {
           return this.index
       }
    },
    methods: {    
       closeBox() {
           this.$parent.messages.splice(this.getIndex,1)
       }
    },
    mounted() {
       this.id = _.uniqueId('message_')
    },
    beforeDestroy() {
      clearTimeout(this.timeout)
    },
    watch: {

    }
}
</script>
<style>
  .info {
      position: absolute;
      display: inline-block;
      background-color: #8ca6d8;
      margin-left:10%;
      padding: 20px;
      max-width: 90%;
      min-width: 70%;
      color:white;
      text-align: center;
      max-height: 250px;
      min-height: 40px;
      border-radius: 1%;
      letter-spacing: 1px;
      word-spacing: 2px;
  }
  .warn {
       position: absolute;
      display: inline-block;
      background-color: #e2c55d;
      margin-left:10%;
      padding: 20px;
      max-width: 90%;
      min-width: 70%;
      color:white;
      text-align: center;
      max-height: 250px;
      min-height: 40px;
      border-radius: 1%;
      letter-spacing: 1px;
      word-spacing: 2px;
  }
  .error {
      position: absolute;
      display: inline-block;
      background-color: #db8874;
      margin-left:10%;
      padding: 20px;
      max-width: 90%;
      min-width: 70%;
      color:white;
      text-align: center;
      max-height: 250px;
      min-height: 40px;
      border-radius: 1%;
      letter-spacing: 1px;
      word-spacing: 2px;
  }
  .close {
      float:right;
      cursor:pointer;
      font-size: 30px;
      font-weight: bold;
  }
  .messageBox-enter-active, .messageBox-leave-active {
   transition: opacity 2s;
  }
  .messageBox-leave-to , .messageBox-enter-to {
   opacity: 0;
}

</style>
