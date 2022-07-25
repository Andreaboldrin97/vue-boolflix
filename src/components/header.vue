<template>
    <header>
        <nav class="bg-dark px-5 py-3 d-flex">
            <div class="pe-4 navbar navbar-dark">
                <button class="navbar-toggler " type="button" @click="$emit('isNavOpen' , true)">
                    <span class="navbar-toggler-icon btn-nav"></span>
                </button>
            </div>
            <div class="d-flex justify-content-between w-100 align-items-center logo-text">
                    <a class="navbar-brand text-danger " href="#">BOOLFIX</a>
                    <div>
                        <input class="form-control me-2" placeholder="Search" v-model.trim="searchInput" @keyup.enter="$emit('search' , searchInput)">
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
header{
    height: 88px;
}
.logo-text{
    a{
        font-size: 35px;
        font-weight: bold;
    }
    
}
</style>