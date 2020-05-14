<template>
    <div>    
        <input type="button" value="Add Contact" @click="this.getModalChain" class="add-contact"> 
        <input type="button" value="Search Contact" @click="this.getModalChain" class="search-contact">             
        <div id="contacts-wrapper"> 
            <template v-for="(item, index) in contacts">      
                <div class="contacts">
                    <div class='contact-name'>ID: {{index}}</div>
                    <div class='contact-name'>Name: {{item.name}}</div>
                    <div class='contact-phone'>Phone: {{item.phone}}</div>
                    <input type="button" value="change" @click="changeElementChain(item)">
                    <input type="button" value="delete" @click="removeElementChain(index)">
                </div>
            </template>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        contacts:{
            type: Array
        },
        changeElement:{
            type: Function
        },
        removeElement:{
            type: Function
        },
        getModal:{
            type: Function
        }        
    },
    methods:{
        changeElementChain: function(item){
            this.changeElement(item)
        },
        removeElementChain: function(index){
            this.removeElement(index)
        },
        getModalChain: function(e){
            this.getModal(e)
        }
    }
}
</script>