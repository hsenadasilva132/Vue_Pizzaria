<template>
    <div>
       <nav>
        <router-link to="/"> <!--to definido com barra para indicar que ao clicar no logo vai direcionar para o home-->
            <img src="" alt="">
        </router-link>
           <router-link to="/">Home</router-link> |
           <router-link to="/Pedidos">Pedidos</router-link>
      </nav>
    </div>
</template>

<script>
export default {
    name: "Navbar"
}
</script>

<style>
    
</style>