                    </div>
                    <div class="input-container">
                        <label for="queijos">Escolha o queijo da sua pizza:</label>
                    <select name="queijos" id="queijos" value="" v-model="queijo">
                        <option value="" name="queijo" :v-model="queijo">Selecione o tipo de queijo</option>
                        <option v-for="queijos in queijo" :key="queijos.id" :value="queijos.data"> 
                            {{ queijos.tipo }}</option>
                    </select>
                    </div>
                    <div id="opcionais-container" class="input-container">
                        <label id="opcionais-title" for="opcionais">Selecione os opcionais:</label>
                        <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                            <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.data">
                            <span>{{ opcional.tipo }}</span>
                        </div>         
                    
                    </div>
                    <div class="input-container">
                        <input type="submit" class="submit-btn" value="CRIAR MINHA PIZZA!">
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
     name: "PizzForm",
     data() {
        return {
            //dados do servidor 
            massas: null,
            queijo: [],
            opcionaisdata: null,
            //
            nome: null,
            massa: [],
            queijos: [],
            opcionais: [],
            status: "solicitado",
            msg: null

        }
     },
     methods: {
        async getIngredientes() {

            const req = await fetch("http://localhost:3000/ingredientes"); //Esse código faz uma requisição assíncrona e aguardando a resposta
            const data = await req.json(); //Esperando resolver a requisição, transformar em json para poder ter dados.

            console.log(data);

            this.massas = data.massa;
            this.queijo = data.queijos;
            this.opcionaisdata = data.opcionais;
        }
     },
     mounted() {
        this.getIngredientes()
     }
  }
</script>

<style scoped>
    #pizz-form {
        max-width: 400px;
        margin: 0 auto;
    }

  .input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;

  }

  label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #E6531D;
  }

  input, select {
    border: 2px solid #222;
    padding: 5px 10px;
    width: 300px;
  }

  #opcionais-container {
    flex-direction: row;
    flex-wrap: wrap;
  }

  #opcionais-title {
    width: 100%;
  }

  .checkbox-container {
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
  }

 .checkbox-container span,
 .checkbox-container input {
    width: auto;
 }

 .checkbox-container span {
    margin-left: 6px;
    font-weight: bold;
 }

 .submit-btn {
    background-color: #222;
    color: #E6531D;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    margin-right: 105px;
    cursor: pointer;
    transition: .5s;
 }

 .submit-btn:hover {
    background-color: #E6531D;
    color: #222;
    
 }
</style>