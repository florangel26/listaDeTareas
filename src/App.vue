<template>
  <div id="app">
    <h1>LISTADO DE TAREAS</h1>
    <label>
      <input
        type="text"
        v-model="tarea"
        placeholder="Ingrese una nueva tarea"
      />
    </label>
    <button
      type="button"
      id="boton"
      class="btn btn-primary mx-2"
      @click="addTarea"
    >
      Crear
    </button>
    <h2>Tareas</h2>
    <ul v-for="(tarea, index) in tareas" :key="index" class="list-group">
      <li class="list-group-item">
        <strong>{{ index }}: {{ tarea }}</strong>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tarea: "",
      tareas: [],
    };
  },
  methods: {
    addTarea() {
      const { tarea } = this;
      this.tareas.push(tarea);
      this.tarea = "";
    },
  },
};
</script>

<style>
#all {
  background-image: url(assets/fondo.jpg);
  background-size: cover;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

#app {
  width: 50%;
  min-height: 500px;
  text-overflow: clip;
  background-color: rgb(255, 253, 250);
  font-family: "Grape Nuts", cursive;
  text-align: center;
  color: #333;
  margin-top: 60px;
}
h1 {
  margin: 20px;
}
.list-group {
  width: 300px;
  margin: 0 auto;
}
h2 {
  display: block;
  text-align: center;
  font-size: 25px;
}
#boton {
  width: 80px;
  margin: 0 auto;
  background-color: black;
}
</style>
