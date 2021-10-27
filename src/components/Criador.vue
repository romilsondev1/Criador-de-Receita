<template>
<div id="create">
  <h1>Criador de Receita</h1>
  <div id="conteudo-left">
    <h3 id="form">Monte a sua Receita</h3>
    <form id="mount" action="">
      <label for="titulo">Titulo</label><br>
      <input id="titulo" type="text" v-model="titulo"><br><br>
      <label for="image">Insira uma imagem ilustrativa</label><br>
      <input type="file" accept="image/jpeg" @change=uploadImage><br><br>
      <label for="texto">Ingredientes</label><br><br>
      <textarea type="text" id="text" name="fname" v-model="receita"></textarea><br><br>
      <button id="btn">Criar Receita</button>
    </form>
  </div>
  <div id="conteudo-right">
    <h3>Preview</h3>
    <div >
      <h2>{{titulo}}</h2>
    <img v-bind:src="previewImage" class="img-preview" />
      <p>{{receita}}</p>
    </div>
  </div>
</div>
</template>

<script lang="js">
    export default {
        name:'imageUpload',
        data(){
            return{
               previewImage:null,
               titulo: "",
               receita:""
            }
        },
        methods:{
            uploadImage(e){
                const image = e.target.files[0];
                const reader = new FileReader();
                reader.readAsDataURL(image);
                reader.onload = e =>{
                    this.previewImage = e.target.result;
                    console.log(this.previewImage);
                };
            }
        }
     }  // missing closure added

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


#conteudo-left{
  /*Novamente definimos a largura da div*/
  width:500px;
  /* altura da div */
  height: auto;
  /* O atributo Float é utilizado para fazermos o nosso bloco(div)
  literalmente flutue e se posicione onde queremos na página,
  quando escolhemos left, dizemos que esse bloco irá se posicionar na
  parte esquerda da página */
  float:left;
  /* Cor de fundo da div */
  background-color:rgb(126, 126, 126);
  border-radius: 5px;
  margin-left: 50px;

  }
#conteudo-right{
  /*Novamente definimos a largura da div*/
  width:700px;
  /* altura da div */
  height:auto;
  /* Pode parecer meio estranho usarmos o mesmo atributo left para o bloco
  em que queremos posicionar na direita, mas como sabemos, o CSS é um estilo
  em cascata, nossa div conteúdo definimos a largura de 1000px e na
  conteudo-left 500px, automaticamente ao definirmos o conteudo-right
  com 500px e à esquerda também, ele ficou à direita do conteudo-left,
  pois o máximo que a div filha poderá ter é 1000px, sendo 500+500=1000px */
  float:left;
  /* Cor de fundo da div */
  background-color:rgb(243, 243, 243);
  border-radius: 5px;
  margin-left: 20px;
  border:solid;
  border-color: rgba(46, 167, 110, 0.6);
  }

input {
  padding-top: 20px;
}

label {
  padding-top: 20px;
}

h3#form{
  color:whitesmoke
}

#mount{
 text-align: left;
 padding-left: 20px;

}

#text{
  border-radius: 5px;
}

#btn{
  background-color: rgb(46, 167, 110);
  border:none;
  border-radius: 10px;
  color:whitesmoke;
  padding:10px;
  margin-top: 5px;
  float:left;
  margin-bottom: 20px;
  cursor:pointer

}

.img-preview{
  width: 500px;
}

#titulo{
  border-radius: 5px;
  height: 10px;
  width: 300px;
  padding: 5px;
}

label{
  color: aliceblue;
  font-size: 14px;
}
</style>
