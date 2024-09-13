<template>
    <div>
        <div id="pizza-table">
            <div>
                <div id="pizza-table-heading">
                    <div class="order-id">#</div>
                    <div>Cliente</div>
                    <div>Massa:</div>
                    <div>Queijo:</div>
                    <div>Opcionais:</div>
                    <div>Ações:</div>
                </div>
            </div>
            <div id="pizza-table-rows">
                <div class="pizza-table-row" v-for="(item, index) in pizza" :key="index">
                    <div class="order-number">{{ item.id }}</div>
                    <div>{{ item.nome }}</div>
                    <div>{{ item.massa }}</div>
                    <div>{{ item.queijos }}</div>
                    <div>
                        <!--
                        Ajuste interno:
                        O problema estava sobre pizza.opcionais que estava iterando errado, 
                        fazendo com que todos os opcionais fossem exibidos.
                        
                        Solução:
                        item.opcionais itera corretamente, buscando os opcionais de cada pizza especifica.
                        --> 
                        
                        <ul>
                            <li v-for="(opcional, opciIndex) in item.opcionais" :key="opciIndex">
                                {{ opcional }}  
                            </li>
                        </ul>
                    </div>
                    <div>
                    <select name="status" class="status">
                        <option value="">Selecione</option>
                        <option v-for="s in status" :key="s.id" :value="s.id">
                            {{ s.tipo }}
                        </option>
                    </select>
                    <button class="delete-btn">Cancelar</button>
                </div>
                    
                </div> <!---->
            </div>
        </div>  
    </div>
</template>

<script>


  export default {
    name: 'Dashboard',
    data() {
        return {
            pizza: null,
            pizzas_id: null,
            status: []
        }
    },
    methods: {
        async getPedidos() {

            const req = await fetch("http://localhost:3000/pizzas");

            const data = await req.json();

            this.pizza = data;
            
            console.log(this.pizza);

            //resgatar os status
            this.getStatus();
        },
        async getStatus() {
            const req = await fetch("http://localhost:3000/status");

            const data = await req.json(); //Adicionado await, 
            /* 
            sem o await a promisse estava sendo atribuida para a variável data,
            e não aos dados reais.
            O await faz com que a função assíncrona pause até que a promessa seja resolvida,
            permitindo que trabalhe diretamente com os dados reais.
            */

            console.log('Status data:', data); 

            this.status = data;

            
        }
    },
    mounted() {
       this.getPedidos("componente montado");
       this.getStatus();
    },
  }
</script>

<style scoped>
   #pizza-table {
    max-width: 1200px;
    margin: 0 auto;
   }

   #pizza-table-heading,
   #pizza-table-rows,
   .pizza-table-row {
    display: flex;
    flex-wrap: wrap;
   }

   .pizza-table-row div {
    font-weight: bolder;
   }

   #pizza-table-heading {
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid #333;
   }

   #pizza-table-heading div,
   .pizza-table-row div {
    width: 19%;
   }

   .pizza-table-row {
    width: 100%;
    padding: 12px;
    border-bottom: 1px solid #CCC;
   }

   #pizza-table-heading .order-id,
   .pizza-table-row .order-number {
    width: 5%;
   }

   select {
    padding: 12px 6px;
    margin-right: 12px;
   }

   .delete-btn {
    background-color: #222;
    color: #E6531D;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: 0.5s;
   }

   .delete-btn:hover {
    background-color: #E6531D;
    color: #222;
   }
</style>
