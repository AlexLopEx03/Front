<script setup>
const fetchData = async () => {
  try {
    const res = await fetch('http://localhost:8000/');
    if (!res.ok) throw new Error('Error en la respuesta');
    const data = await res.json();
    alert(JSON.stringify(data));
  } catch (error) {
    alert('Error: ' + error.message);
  }
}
</script>

<template>
  <button @click="fetchData">Haz fetch</button>
</template>
