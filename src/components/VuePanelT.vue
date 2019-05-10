<template>
   <div>
          <VueAccordin>
               <VueAccordinPanel name="panel1">
                     React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
               </VueAccordinPanel>
               <VueAccordinPanel name="panel2">
                    Panel2
               </VueAccordinPanel>
               <VueAccordinPanel name="panel3">
                    React (also known as React.js or ReactJS) is a JavaScript library[3] for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.[4][5][6]
            React can be used as a base in the development of single-page or mobile applications, as it's optimal only for its intended use of being the quickest method to fetch rapidly changing data that needs to be recorded. However, fetching data is only the beginning of what happens on a web page, which is why complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API.[7][8]
               </VueAccordinPanel>
                <VueAccordinPanel name="panel4">
                    Panel4
               </VueAccordinPanel>
          </VueAccordin>
    </div>
</template>
<script>
import VueAccordin from '../generic/VueAccordin'
import VueAccordinPanel from '../generic/VueAccordinPanel'

export default {
    name: 'VuePanelT',
    components: {
        VueAccordin,
        VueAccordinPanel
    },
    methods: {

    },
    mounted() {

    }
}
</script>
<style>

</style>