<script setup>
const fetchData = async () => {
  try {
    const res = await fetch('https://obscure-space-funicular-97x7pgg65g9cpxqx-8000.app.github.dev/');
    if (!res.ok) {
      const text = await res.text(); // por si no es JSON
      throw new Error(`HTTP ${res.status}: ${text}`);
    }
    const data = await res.json();
    alert(JSON.stringify(data));
  } catch (error) {
    alert('Error: ' + error);
  }
}
</script>


<template>
  <button @click="fetchData">Haz fetch</button>
</template>
