                    <div id="opcionais-container" class="input-container">
                        <label id="opcionais-title" for="opcionais">Selecione os opcionais:</label>
                        <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                            <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.data">
                            <span>{{ opcional.tipo }}</span>
                        </div>         
            opcionaisdata: null,
            opcionais: [],
            const req = await fetch("http://localhost:3000/ingredientes"); //Esse código faz uma requisição assíncrona e aguardando a resposta
            const data = await req.json(); //Esperando resolver a requisição, transformar em json para poder ter dados.
            this.opcionaisdata = data.opcionais;
