<template>
    <div id='modal-form'>
        <div id='modal-wrapper'>            
          <template v-if='modalService.add'>
            <AddForm  :getModal='getModal' :closeModal='closeModal' :pushContact='pushContact'/>            
          </template>
          <div v-else>             
            <SearchForm :searchElement='searchElement' :getModal='getModal' :closeModal='closeModal'/>            
          </div>  
        </div>
    </div>          
</template>

<script>



export default {
    components:{
        AddForm: () => import('./ModalComponents/AddForm.vue'),
        SearchForm: () => import('./ModalComponents/SearchForm.vue'),        
    },
    props: {  
        searchElement:{
            type: Function
        },
        modalService:{
            type: Object
        },
        getModal: {
            type: Function
        },
        pushContact:{
            type: Function
        },
        closeModal:{
            type: Function
        }
    }
}
</script>

<style scoped>
@import "../../css/main.css"
</style>