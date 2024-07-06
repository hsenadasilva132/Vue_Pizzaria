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

<style scoped>
      nav {
    background-color: #222;
    border-bottom: 4px solid #111;
    padding: 15px 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
   }

   #logo-url {
    margin: auto;
    margin-left: 0;
   }

   img {
    width: 40px;
    height: 40px;
   }

   nav a {
    color: #FCDA03;
    text-decoration: none;
    margin: 12px;
    transition: .5s;
   }

   nav a:hover {
    color: #FFF;
   }
</style>