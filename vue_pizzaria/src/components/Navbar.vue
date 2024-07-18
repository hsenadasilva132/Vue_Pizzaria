<template>
    <div>
       <nav>
        <router-link to="/" id="logo-url"> <!--to definido com barra para indicar que ao clicar no logo vai direcionar para o home-->
            <img :src="logo" :alt="alt">
        </router-link>
           <router-link to="/" class="options-nav">HOME</router-link> |
           <router-link to="/Pedidos" class="options-nav">PEDIDOS</router-link>
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
    border-bottom: 2px solid #E6531D;
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
    color: #E6531D;
    font-size: 0.8em;
    font-weight: 700;
    text-decoration: none;
    margin: 12px;
    transition: .5s;
   }

   nav a:hover {
    color: #FFF;
   }
</style>