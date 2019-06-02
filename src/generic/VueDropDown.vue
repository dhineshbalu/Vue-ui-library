<template>
<div class="dropdown">
  <button class="dropbtn">Dropdown</button>
  <div class="dropdown-content">
     <a v-show="showBack" style="background-color:grey;" @click="goBack">&laquo;<span style="font-weight:bold;float:right;" >Back</span></a>
    <a v-for="(list,index) in getTop" :key="index" @click="selectedDrop(list.code,list.children)">{{list.label}}
         <span style="float:right"  v-show="list.children.length">&raquo;</span>
    </a>
  </div>
</div>
</template>
<script>
export default {
    name: 'VueDropDown',
    props: {
       id: {
           type: String
       },
       datas: {
           type: Array
       }
    },
    data() {
        return {
           current: []
        }
    },
    computed: {
        getTop() {
            return this.current[this.current.length-1]
        },
        showBack() {
            return this.current.length > 1
        }
    },
    methods: {
       selectedDrop(code,children) {
         if (children.length) {
             this.current.push(children)
         } else {
             this.$events.emit('gc:dropdown' , {
                 code: code
             })
         }
       },
       goBack() {
           this.current.pop()
       }
    },
    mounted() {
       this.current.push(this.datas)
    }
}
</script>
<style>
.dropbtn {
  background-color: #4CAF50;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}

.dropdown {
  cursor: pointer;
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .dropbtn {
  background-color: #3e8e41;
}
</style>