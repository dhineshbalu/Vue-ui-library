<template>
     <div :style="styleContainer" >
          <div :style="styleHead" >
              <slot  name="head"></slot>
            </div>
            <div :style="styleBody">
                <slot name="body"></slot>
            </div>
            <div :style="styleFooter">
                <slot name="footer"></slot>  
             </div>
                  
      </div>
</template>
<script>
export default {
    name: 'VueCards',
    props: {
       color: {
           type: String,
           default: 'black'
       }
    },
    created() {

    },
    computed: {
        styleContainer() {
         return {
            maxWidth: '25%',
            maxHeight: '25%',
            borderWidth: '2px',
            borderColor: this.color,
            borderStyle: 'solid'
         }
        },

      styleHead() {
        return {
            borderColor: this.color,
            textAlign: 'center',
            color:'white',
            paddingTop:'10px',
            paddingBottom:'10px',
            letterSpacing: '1px',
            fontWeight: 'bold',
            backgroundColor: this.color,
            letterSpacing: '2px'
          }
        },
        styleBody() {
            return {
                paddingTop: '10px',
                paddingBottom: '10px',
                margin:'5px',
                letterSpacing: '1px',
                wordSpacing: '2px',
                textAlign: 'center',
                wordWrap: 'break-word'
            }
        },
        styleFooter() {
            return {
                backgroundColor: this.color,
                paddingTop: '10px',
                paddingBottom: '10px',
                letterSpacing: '2px',
                color:'white',
                fontWeight: 'bold',
                textAlign: 'center',
            }
        }
    },
    methods: {
      
       }
    ,
    watch: {

    }
}
</script>
