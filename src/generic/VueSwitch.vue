<template>
  <label class="switch">
    <input :id="id" type="checkbox" :checked="checked" :disabled="disabled" @change="changeToggle">
    <span class="slider round"></span>
    <span v-html="sliderText"></span>
  </label>
</template>
<script>
export default {
  name: 'VueSwitch',
  props: {
    id: {
    type: String
    },
    checked: {
      type: Boolean,
      default: false
    },
    on: {
      type: String
    },
    off: {
      type: String
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      val: ''
    }
  },
  computed: {
   sliderText() {
     return `<strong class="text">${this.val}</strong>`
   }
  },
  methods: {
    changeToggle(event) {
      if (event.target.checked) {
         this.val = this.on
      } else {
        this.val = this.off
      }
      this.$emit('input',this.val)
    },
    controls(task,val) {
      switch(task) {
        case 'disable':
                this.disabled = val
                break
        case 'checked':
                this.checked = val
                break
      }
    }
  },
  mounted() {
     if (this.checked) {
       this.val = this.on
     } else {
       this.val = this.off
     }
     this.$events.on('gc:switch',(o) => {
       let str = o.task.split('|')
        if (this.id == o.id) {
           if (str[0] == 'control') {
               this.controls(str[1],o.data)
            }
        }
     })
  }
}
</script>
<style>
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input { 
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #2196F3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
.text {
  padding-top:20px;
  padding-left: 5px;
  display: inline-block;
}
</style>