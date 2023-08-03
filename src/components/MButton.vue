<script setup>
const props = defineProps({
  text: String
})
</script>

<template>
  <button>
  <slot>
  {{ props.text }}
  </slot>
  </button>
</template>

<style scoped>
.primario {
  background-color: #007bff;
}
.primario:hover {
  background-color: #0069d9;
}

.secundario {
  background-color: #6c757d;
}
.secundario:hover {
  background-color: #5a6268;
}

.terciario {
  background-color: #28a745;
}
.terciario:hover {
  background-color: #218838;
}

.perigo {
  background-color: #dc3545;
}
.perigo:hover {
  background-color: #c82333;
}
.alerta {
  background-color: #ffc107;
}
.alerta:hover {
  background-color: #e0a800;
}
.sucesso {
  background-color: #28a745;
}
.sucesso:hover {
  background-color: #218838;
}
.info {
  background-color: #17a2b8;
}
.info:hover {
  background-color: #138496;
}
.escuro {
  background-color: #343a40;
}
.escuro:hover {
  background-color: #23272b;
}
.claro {
  background-color: #f8f9fa;
}
.claro:hover {
  background-color: #dae0e5;
}
button {
  background-color: blue;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px;
  font-size: 1.2rem;
  cursor: pointer;
  margin: 5px;
}

button:hover {
  background-color: darkblue;
}
</style>