<template>
 <div>
           <VueTab id="tab">
                <VueTabPane id="pane1" name="panel1">
                   panel1
                </VueTabPane>
                <VueTabPane id="pane2" name="panel2">
                    panel2
                </VueTabPane>
                <VueTabPane id="pane3" name="panel3">
                   Panel3
                </VueTabPane>
                 <VueTabPane id="pane4" name="panel4">
                   Panel4
                </VueTabPane>
           </VueTab>
           
  </div>
</template>
<script>
import VueTab from '../generic/VueTab'
import VueTabPane from '../generic/VueTabPane'
    export default {
        name: 'VueTabT',
        components: {
           VueTab,
           VueTabPane
        },
        data() {
            return {

            }
        }
    }
</script>