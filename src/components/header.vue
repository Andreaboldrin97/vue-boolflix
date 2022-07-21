<template>
    <header>
        <nav class="navbar navbar-expand-lg bg-dark px-5 py-3">
            <div class="container-fluid">
                <a class="navbar-brand text-danger" href="#">BOOLFIX</a>
                <!-- <button class="navbar-toggler">
                    <span class="navbar-toggler-icon"></span>
                </button> -->
                <div>
                    <input class="form-control me-2" placeholder="Search" v-model.trim="searchInput" @keyup.enter="$emit('search' , searchInput)">
                    <button @click.prevent="" class="btn btn-outline-danger">Search</button>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    data : function(){
        return{
            searchInput : '',
        }
    },
    methods :{
        log : function(element){
            console.log(element)
        }
    }

}
</script>

<style lang="scss">

</style>