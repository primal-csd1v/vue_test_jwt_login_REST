<template>
    <div>
        <h1>contact search</h1>       
        <h3>by name</h3>
        <div><input type="text" v-model="name"></div>
        <h3>by phone number</h3>
        <div><input type="text" v-model="phone"></div>
        <input type="button" value="Search" @click="searchElementChain({name:name,phone:phone})">
        <input type="button" value="Exit" class='exit-search' @click="closeModalChain">
    </div> 
</template>

<script>
export default {
    props:{
        searchElement:{
            type: Function
        },
        dataModal: {
            type: Object
        },
        getModal: {
            type: Function
        },
        closeModal:{
            type: Function
        }
    },
    data(){
        return{
            name: '',
            phone: null
        }
    },
    methods:{
        closeModalChain:function(){
            this.closeModal()
        },
        searchElementChain: function(obj){
            this.searchElement(obj)
        }
    }
}
</script>