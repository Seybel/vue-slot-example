<template>
    <div>
        <div><h1>Hello from Child</h1></div>
        <slot :msg="msg" :hello="hello"/>
        <slot name="multiply" :square="number * number" :double="number * 2"></slot>
    </div>
</template>

<script>
    export default {
        props: {
            number: {
                type: Number,
                default: null
            },
        },
        
        data() {
            return {
                msg: 'This is from the child unnamed slot-scope'
            }
        },

        methods: {
            hello() {
            window.alert('THIS IS FROM THE CHILD') 
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>