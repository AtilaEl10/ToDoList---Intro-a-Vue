<template>
  <div id="app">
    <img alt="to do list icono" src="./assets/header.png">
    
    <h1 class="fw-bold my-4 text-secondary"> Tareas por realizar</h1>

    <input v-model="tareas" class="mx-4" type="text">
    <button @click="ingresarTarea()" class="btn btn-outline-info">Agregar</button>

    <ol class="my-5 mx-auto">
      <li v-for="tareas in todolist" :key="tareas">
        {{tareas}}
      </li>
    </ol>
    <div class="d-grid gap-2 col-4 mx-auto">
      <button @click="limpiar()" class="btnlimpiar btn btn-danger fw-bold my-4">Limpiar</button>
    </div>
  </div>
</template>

<script>
export default {
  
  name: "App",
  data() {
    return {
      todolist: [],
      tareas: ""
    }
  },
  methods: {
    ingresarTarea(){
      if (this.tareas === "") return;
      this.todolist.push(this.tareas);
      this.tareas = ""
    },
    limpiar(){
      this.todolist = []
    }
  }
}

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  font-family: 'Nanum Pen Script', cursive;
  font-size: 55px;
}
img {
  width: 20%;
}
button {
  height: 40px;
}
.btnlimpiar {
  font-size: 20px;
}
input {
  height: 40px;
  width: 300px;
}
ol {
  font-family: 'Nanum Pen Script', cursive;
  display: flex;
  flex-direction: column;
  width: 60%;
  font-size: 45px;
  align-items: center;
}
</style>
