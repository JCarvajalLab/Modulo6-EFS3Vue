<template>
  <div class="table-container">
    <div class="header">Tienda Bit-Game</div>
    <div class="welcome">
      <h1>¡Bienvenido!</h1>
      <p>A continuación encontrarás la lista de los juegos que prefieres</p>
    </div>

    <table>
        <thead>
        <tr>
            <th>#</th>
            <th>Juego</th>
            <th>Eliminar juego de tu lista</th>
        </tr>
    </thead>
        <tbody>
        <tr v-for="(juego, index) in juegos" :key="juego">
          <td>{{ index }}</td>
          <td>{{ juego }}</td>
          <td>
            <button class="btn-eliminar" @click="eliminarJuego(index)">
              Eliminar
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "BuscadorProducto",
  props: {
    juegos: Array,
  },
  methods: {
    eliminarJuego(index) {
      this.$emit("eliminar-juego", index);
    },
  },
};
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}
.header {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 20px 0;
  font-size: 24px;
}
.welcome {
  background-color: #e0f7fa;
  padding: 20px;
  margin: 20px;
  border-radius: 5px;
}
.welcome h1 {
  margin: 0;
  font-size: 24px;
}
.welcome p {
  margin: 10px 0 0 0;
  font-size: 16px;
}
.table-container {
  margin: 20px;
}
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}
table,
th,
td {
  border: 1px solid #333;
}
th,
td {
  padding: 10px;
  text-align: center;
}
th {
  background-color: #333;
  color: white;
}
td {
  background-color: #444;
  color: white;
}
.btn-eliminar {
  background-color: #e74c3c;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}
.btn-eliminar:hover {
  background-color: #c0392b;
}
</style>
