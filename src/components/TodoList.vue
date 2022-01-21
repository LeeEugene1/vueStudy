<template>
    <div>
        <div>
            <input type="text" v-model="inputValue">
            <button @click="addItem">add</button>
        </div>
        <ul>
            <ListItem v-for="(value,index) in listArray" 
            :key="index" 
            :index="index"
            :text="value === '' ? undefined : value"
            @delete="catchEmitProps"
            />
        </ul>
    </div>
</template>

<script>
import ListItem from './ListItem.vue'

export default {
    data(){
        return{
            inputValue:"",
            listArray:[]
        }
    },
    components:{
        ListItem
    },
    methods:{
        addItem(){
            this.listArray.push(this.inputValue);
            this.inputValue = "";
        },
        catchEmitProps(index){
            this.listArray.splice(index,1)//index포함 1개만 없애겠다.
        }
    }
}
</script>
<style>
    
</style>