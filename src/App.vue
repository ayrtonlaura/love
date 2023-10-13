<template>
  <div>
    <button @click="btnCancelar" >Cancelar</button>
    <button
      @mouseover="moveButton"
      @click="moveButton"
      :style="{ top: buttonTop + 'px', left: buttonLeft + 'px' }"
    >
      Mueve el Botón
    </button>
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
      alert("Ayrton2");
    }
  },
};
</script>

<style>
button {
  position: absolute;
}
</style>
