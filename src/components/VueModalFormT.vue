<template>
   <VueModalForm>
       <h2 slot="head">Title </h2>
       <div slot="body">
           React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
            React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
              React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
            React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
         React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
            React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
         React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
            React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
        React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
          React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
       
        </div>
        <div slot="footer">
          <VueButton style="float:right" type="positive" size="xsmall" @click="buttonMethod">submit</VueButton>
          <VueButton style="float:right"  type="negative" size="xsmall" @click="buttonMethod">cancel</VueButton>
        </div>
   </VueModalForm>
</template>
<script>
import VueModalForm from '../generic/VueModalForm'
import VueButton from '../generic/VueButton'
export default {
    name: 'VueModalFormT',
    components: {
     VueModalForm,
     VueButton
    },
    methods: {
      buttonMethod() {
          this.$events.emit('changeActive','')
      }
    },
    mounted() {
       this.$events.on('close',()=> {
            this.$events.emit('changeActive','')
       })
    }
}
</script>