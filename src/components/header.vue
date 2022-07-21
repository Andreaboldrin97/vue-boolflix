<template>
    <header>
        <nav class="navbar navbar-expand-lg bg-dark px-5 py-3">
            <div class="container-fluid">
                <a class="navbar-brand text-danger" href="#">BOOLFIX</a>
                <button class="navbar-toggler">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div>
                    <form class="d-flex" role="search">
                        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" v-model="searchImput" >
                        <button class="btn btn-outline-danger" type="submit">Search</button>
                    </form>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    data : function(){
        return{
            searchImput : '',
        }
    }

}
</script>

<style lang="scss">

</style>