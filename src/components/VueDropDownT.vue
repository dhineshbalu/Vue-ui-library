<template>
<div>
     <VueDropDown id="drop1" :datas="lists"></VueDropDown>
</div>
</template>
<script>
export default {
    name: 'VueDropDownT',
    props: {

    },
    data() {
        return {
            lists: [{
                code: '1A',
                label: 'first',
                children: []
            }, {
                 code: '2A',
                label: 'second',
                children: [] 
            } , {
                   code: '3A',
                label: 'third',
                children: [ {
                code: '3A1',
                label: 'fourth',
                children: [] 
                }, {
                 code: '3A2',
                label: 'fifth',
                children: [{
                    code: '3A21',
                    label:'sixth',
                    children: [{
                        code: '3A211',
                        label: 'seventh',
                        children: []
                    }]
                }] 
                }] 
            }]
        }
    }
}
</script>
<style>

</style>