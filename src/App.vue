<template>
  <div >
    <h1>v-html</h1>
    <div v-html="html"></div>

    <hr>
    <h1>v-show</h1>
    <h3>Tu edad es: {{edad}}</h3>
    <h2 v-if="edad >= 18 && edad > 0 && edad < 100">Mayor de edad</h2>
    <h2 v-else-if="edad < 18 && edad >0 && edad<100">Menor de edad</h2>
    <h2 v-else>Edad invalida</h2>
    <button @click="inc()">incrementar</button>
    <button @click="dis()">disminuir</button>

    <hr>
    <h1>v-for</h1>
    <ul>
      <li>{{usuarios[0]}}</li>
      <li>{{usuarios[1]}}</li>
      <li>{{usuarios[2]}}</li>
      <li>{{usuarios[3]}}</li>
    </ul>
    <br>
    <ul>
      <li v-for="usuario in usuarios">{{usuario}}</li>
    </ul>
    <br>
    <ul>
      <li v-for="(usuario,index) in usuarios">{{usuario}}:{{index}}</li>
    </ul>
    <br>
    <ul>
      <li v-for="(valor,clave) in uusaurios" :key="clave">{{clave}}:{{valor}}</li>
    </ul>
    <hr>
    <h1>v-bind</h1>
    <img v-bind:src="url" alt="No hy internet">
  </div>
  <hr>

  <h1>v-on</h1>
  <div @dblclick="click" class="contador">
    clicks:{{clicks}}
  </div>
</template>


<script>
  export default{
    data:()=>({
      titulo:"Hola desde VUE.js",
      html:"<h3>Soy un h3</h3>",
      edad:0,
      usuarios:["Melisa","Fernando","Raul","Jose"],
      uusaurios:{nombre:"Yirsis"},
      clicks:0,
      url: "https://cdn.svgporn.com/logos/replit-icon.svg",
    }),
    methods:{
      inc(){
        this.edad++;
      },
      dis(){
        this.edad--;
      },
      click(){
        this.click++;
      },
    },
  };
</script>


<style scoped>
  div{
    text-align: center;
    margin: 0px 2rem;
  }
  h2{
    color: tomato;
  }
  .contador{
    background: pink;
    color: snow;
    font-weight: bold;
    height: 400px;

  }
</style>