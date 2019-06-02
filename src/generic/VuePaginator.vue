<template>
 <div class="pagination">
  <a @click="prevChunk" :class="checkValidC(-1)">&laquo;&laquo;</a>
  <a @click="prev" :class="checkValidP(-1)">&laquo;</a>
  <a v-for="(list,index) in pages" :key="index" :class="activePage(list)" @click="selectedPage(list)">{{list}}</a>
  <a @click="next" :class="checkValidP(1)">&raquo;</a>
  <a @click="nextChunk" :class="checkValidC(1)">&raquo;&raquo;</a>
</div>
</template>
<script>
 export default {
     name: 'VuePaginator',
     props: {
       id: {
           type: String
       },
       target: {
           type: String
       },
       chunk: {
           type: Number,
           default: 5
       },
       row: {
           type: Number,
           default: 5
       }
     },
     data() {
         return {
            nodes: [],
            page: 1,
            records: 0
         }

     },
     computed: {
         pages() {
           let p = []
           for(var i=0;i<this.chunk;i++) {
               p[i] = this.pagesInCurrentChunk + i + 1
           }
            if (p[0] == 0)
              p.splice(0,1)
           return p
         },
         totalPage() {
             return Math.floor(this.records/this.row) 
         },
         totalChunks() {
             return Math.floor(this.totalPage/this.chunk) 
         },
         currentChunk() {
             return Math.floor(this.page/this.chunk)  
         },
         paginationStart() {
             return (this.currentChunk)*this.chunk
         },
         pagesInCurrentChunk() {
            return this.currentChunk  == this.totalChunks  ?  Math.abs(this.chunk - this.paginationStart) : this.paginationStart - 1
         }
     },
     methods: {
        checkValidC(n) {
           if (n == -1) {
             return   this.currentChunk == 0 ? 'not-active' : ''
           } else {
               return this.currentChunk > this.totalChunks-1 ? 'not-active' : ''
           }
        },
        checkValidP(n) {
             if (n == -1) {
                 return this.page == 1 ? 'not-active' : ''
             } else {
                 return this.page == this.totalPage  ? 'not-active' : ''
             }
        },
        activePage(n) {
           return this.page == n ? 'active' : ''
        },
        checkValidPage(n) {
            return n >= 1 && n <= this.totalPage
         },
        selectedPage(n) {
            if (this.checkValidPage(n)) {
                this.setPage(n)
            }
         },
        setPage(n) {
           this.page = n
           this.prepareNodes()
       },
        prev() {
         this.selectedPage(this.page-1)
       },
        next() {
         this.selectedPage(this.page+1)
       },
       nextChunk() {
          this.selectedPage(((this.currentChunk+1)*this.chunk))         
       },
       prevChunk() {
          this.selectedPage(((this.currentChunk-1)*this.chunk)+1)
       },
        createNodes() {
           this.nodes = document.getElementById(this.target).getElementsByTagName('tbody')[0].getElementsByTagName('tr')
           for (var i=0;i<this.nodes.length;i++) {
              this.nodes[i].style.display = 'none'
           }
           this.records = this.nodes.length
           this.prepareNodes()
       },
       prepareNodes() {
           var from = (this.page - 1) * this.row
        //    var to = this.page == this.totalPage ?  this.records :from + this.row
        var to = from + this.row > this.records ? this.records : from + this.row
           console.log(from + " " + to)
          
           for(var i=0;i<this.nodes.length;i++) {
               this.nodes[i].style.display = 'none'
           }
            for(var i=from;i<to;i++) {
               this.nodes[i].style.display = 'table-row'
           }
       }
     },
     mounted() {
        this.createNodes()
     },
     watch: {

     }    
 }
</script>
<style>
.pagination {
  display: inline-block;
  cursor: pointer;
}

.pagination a {
  color: black;
  float: left;
  padding: 8px 16px;
  text-decoration: none;
  transition: background-color .3s;
  border: 1px solid #ddd;
}

.pagination a.active {
  background-color: #4CAF50;
  color: white;
  border: 1px solid #4CAF50;
}

.pagination a:hover:not(.active) {background-color: #ddd;}

.not-active {
  pointer-events: none;
  cursor: default;
  text-decoration: none;
  background-color:#707377;
  color:white;
}
</style>