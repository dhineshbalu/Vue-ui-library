<template>
 <div>
      <VueMessaging  v-for="(msg,index) in generateMessages" :key="index" :index="index" :message="msg">

      </VueMessaging>
 </div>
</template>
<script>
export default {
    name: 'VueMessagingT',
    data() {
      return {
          messages: [
              {
                  type: 'info',
                  data: 'first'
                 
              },
               {
                  type: 'info',
                  data: 'second'
              },
               {
                  type: 'info',
                  data: 'third'
                 
              },
              {
                  type: 'warn',
                  data: 'fourth'
              }
          ]
      }
    },
    computed: {
        generateMessages() {
            return this.messages
        }
    }
}
</script>
<style>

</style>
