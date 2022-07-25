<template>
    <div class="nav-user-content bg-dark text-white position-absolute" :class="navIsOpen  ? 'd-block' : 'd-none'">
            <div class="user-profile p-3 d-flex align-items-center border-bottom">
            <img src="../assets/my-img.jpeg" alt="">
            <div class="ps-5">
                LUIGI
            </div>
        </div>
        <div class="p-3 border-bottom">
            <a href="#"><i class="fa-solid fa-download pe-2"></i> I miei dowload</a>
        </div>
        <div class="p-3 listFilter" >
            <div class="py-2" v-for="(element, index) in listUserFilter " :key="index">
                {{ element }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data : function(){
        return{
            listUserFilter : [
                'Home',
                'Serie TV',
                'Film',
                'Originali',
                'Aggiunti di recente',
                'Anime',
                'Film crime',
                'Documentari',
                'Serie TV',
                'Film',
                'Originali',
                'Aggiunti di recente',
                'Anime',
                'Film crime',
                'Documentari',
                'Serie TV',
                'Film',
                'Originali',
                'Aggiunti di recente',
                'Anime',
                'Film crime',
                'Documentari',
                'Serie TV',
                'Film',
                'Originali',
                'Aggiunti di recente',
                'Anime',
                'Film crime',
                'Documentari'
            ],
        }  
    },
    props :{
        navIsOpen : Boolean,
    }

}
</script>

<style lang="scss">
.nav-user-content{
    width: 400px;
    z-index: 1;
        a{
            text-decoration: none;
            color: white;
        }
}
.user-profile{
    img{
        width: 80px;
         object-fit: cover;
    border-radius: 50%;
    max-width: 60px;
    }
}
.listFilter{
    cursor: pointer;
    height: calc(100vh - 238px);
    overflow: auto;
}
</style>