<template>
  <div class="nav-user-content bg-dark text-white">
        <div class="user-profile p-3 d-flex align-items-center border-bottom">
        <img src="../assets/my-img.jpeg" alt="">
        <div class="ps-5">
            LUIGI
        </div>
    </div>
    <div class="p-3">
        <a href="#">I miei dowload</a>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.nav-user-content{
    width: 400px;
    height: calc(100vh - 88px);
}
.user-profile{
    img{
        width: 80px;
         object-fit: cover;
    border-radius: 50%;
    max-width: 60px;
    }
}
</style>