<template>
  <div>
    <h1>hola</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttonTop: 0,
      buttonLeft: 0,
    };
  },
  methods: {
    moveButton() {
      // Calcula nuevas posiciones de manera aleatoria
      const newTop = Math.floor(Math.random() * window.innerHeight);
      const newLeft = Math.floor(Math.random() * window.innerWidth);

      // Actualiza las posiciones en los datos del componente
      this.buttonTop = newTop;
      this.buttonLeft = newLeft;
    },
    btnCancelar(){
      console.log("Ayrton");
    }
  },
};
</script>

<style>
button {
  position: absolute;
}
</style>
