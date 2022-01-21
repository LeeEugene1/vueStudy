<template>
    <li>
        {{text}}
        <button @click="itemDelete">deleteBtn</button>
    </li>
</template>
<script>
export default {
    props:{
        index:{
            type: Number
        },
        text:{
         type: String,
         required: true,
         default: "hello"
        }
    },
    methods:{
        itemDelete(){
            this.$emit('delete', this.index)
        }
    }
}
</script>
<style>
    
</style>