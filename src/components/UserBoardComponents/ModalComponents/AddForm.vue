<template>
    <div>
        <h1>Add new contact</h1>            
        <h3>name</h3>
        <div><input type="text" v-model="name"></div>
        <h3>phone</h3>
        <div><input type="text" v-model="phone"></div>
        <input type="button" value="Add" id='add-btn' @click="pushContactChain">
        <input type="button" value="Exit" id='exit-btn' @click='closeModalChain'>
    </div>
</template>

<script>
export default {
    data(){
        return{
            name: '',
            phone: null
        }
    },
    props:{
        getModal: {
            type: Function
        },
        pushContact:{
            type: Function
        },
        closeModal:{
            type: Function
        }
    },
    methods:{
        getModalChain :function(){
            this.getModal();
        },
        pushContactChain: function(){
            this.pushContact(
                {
                    name: this.name,
                    phone: this.phone
                }
            );
        },
        closeModalChain: function(){
            this.closeModal()
        }
    }
}
</script>