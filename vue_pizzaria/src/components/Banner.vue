<template>
    <div>
       <div id="main-banner">
        <h1>Make Your Pizza</h1>
       </div>
    </div>
</template>

<script>
  export default {
     name: "Banner"
  }
</script>

<style scoped>
  #main-banner {
    background-image: url('../../public/img/pexels-enginakyurt-2260555.jpg');
    background-position: 20% -250px;
    background-size: cover;
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    border-bottom: 4px solid #E6531D;
  }

  #main-banner h1 {
    color: #E6531D;
    text-align: center;
    font-size: 60px;
    background-color: transparent;
    padding: 20px 40px;
  }

  @media(max-width: 375px) {
    #main-banner {
      background-size: cover;
      background-position: 50% 50%;
    }
  }

  @media(max-width: 425px) {
     #main-banner {
      background-size: cover;
      background-position: 40% 60%;
     }
  }

  @media(max-width: 768px) {
    #main-banner {
      background-size: cover;
      background-position: 20% 80%;
    }
  }

  @media(max-width: 1024px) {
    #main-banner {
      background-size: cover;
      background-position: 80% 20%;
    }
  }
</style>