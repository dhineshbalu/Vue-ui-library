<template>
  <div class="modalBox">
       <ul>
           <li  v-for="(list,index) in activeList" :key="index" :class="selectedTabC(list.id)" @click="selectTab(list.id)">{{list.name}}</li>
        </ul>
      <div class="container">
         <slot></slot>
      </div>
  </div>
</template>
<script>
import VueTabPane from './VueTabPane'
 export default {
     name:'VueTab',
     props: {
       id: {
           type: String
       }
     },
     data() {
         return {
           selectedTab: '',
           activeList: []
         }
     },
     components: {
       VueTabPane
     },
     computed: {
         
     },
     methods: {
       selectedTabC(id) {
          return [
            'tabpane',
            this.selectedTab ==id ? 'active' : ''
          ]
       },
      createTabs(values) {
          let t = []
          for(var i=0;i<values.length;i++) {
              t.push({
                  id: values[i].id,
                  name: values[i].name
              }) 
          }
          this.activeList = t
          this.selectTab(this.activeList[0].id)
      },
      selectTab(id) {
         this.selectedTab = id
      }
     },
     mounted() {
         this.createTabs(this.$children)
     }
 }
</script>
<style scoped>
  .tabpane {
    float:left;
    display: inline-block;
    list-style-type: none;
    background-color: black;
    padding: 10px;
    font-weight: bold;
    margin:5px;
    cursor: pointer;
    letter-spacing: 1px;
    text-overflow: ellipsis;
    color:white;
    text-align: center;
    border-radius: 5%;
    outline: none;
    transition: all 1s ease;
  }
  .modalBox {
    max-width: 100%;
    max-height: 100%; 
  }
  .active {
    background-color: white;
    color:black;
  }
  .container {
    clear:left;
    text-align: center;
    max-width: 100%;
    max-height: 100%;
  }
</style>
