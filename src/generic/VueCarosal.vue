<template>
<div>
 <div class="carosal">
   <slot></slot>
 </div>
    <div style="text-align:center;background-color:blueviolet;margin:auto;max-width:1000px;">
     <div v-for="(list,index) in lists" :key="index" :class="selectedCarosal(list)" @click="selectCarosal(list)"></div>  
    </div>
</div>
</template>
<script>
export default {
    name: 'VueCarosal',
    props: {
     id: {
         type: String
     },
     autoplay: {
         type: Boolean,
         default: false
     },
     interval: {
         type: Number,
         default: 2000
     }
    },
    data() {
     return {
         lists: [],
         selected : '',
         index: 0,
         records: 0,
         timeout: ''
     }
    },
    computed: {
      
    },
    methods: {
       selectedCarosal(id) {
           return this.selected == id ? 'active' : 'notactive'
       },
       selectCarosal(id) {
           this.selected = id
       },
       autoPlay() {
           if (this.autoplay) {
             this.timeout =   setInterval(()=> {
                  this.next()
               },this.interval)
           }
       },
       clearAutoPlay() {
           clearInterval(this.timeout)
       },
       next() {
         if (this.index + 1 < this.records) {
             this.index = this.index + 1
         } else {
             this.index = 0
         }
         this.selected = this.lists[this.index]
       }
    },
    mounted() {
        var carosal = []
      for (var i=0;i<this.$children.length;i++) {
        carosal.push(this.$children[i].id)
      }
       this.lists = carosal
       this.records = this.lists.length
       this.selected = this.lists[0]
       this.index = 0
       this.autoPlay()
    },
    beforeDestroy() {
      clearAutoPlay()
    }
}
</script>
<style>
 .active {
     width: 50px;
     height: 8px;
     background-color: white;
     display: inline-block;
     margin-left: 20px;
     cursor: pointer;
     border-radius: 5%;
     transition: 0.4s;
 }
 .notactive {
     width: 30px;
     height: 8px;
     background-color: white;
     display: inline-block;
     margin-left: 20px;
     cursor: pointer;
     border-radius: 5%;
     transition: 0.4s;
 }
 .carosal {
     position: relative;
     max-width: 1000px;
     min-height: 300px;
     max-height: 900px;
     background-color: blueviolet;
     margin:auto;
 }
</style>