<template>
    <div>
       <nav>
        <router-link to="/" id="logo-url"> <!--to definido com barra para indicar que ao clicar no logo vai direcionar para o home-->
            <img :src="logo" :alt="alt">
        </router-link>
           <router-link to="/">Home</router-link> |
           <router-link to="/Pedidos">Pedidos</router-link>
      </nav>
    </div>
</template>

<script>
export default {
    name: "Navbar",
    props: ["logo", "alt"]
}
</script>

<style>
    
</style>