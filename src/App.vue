<template>
  <div class="centered-container">
    <div>
      <h1>Titulo</h1>
    </div>
    <div class="row">
      <button @click="btnCancelar" class="btnCancelar">Cancelar</button>
      <button
        class="btnAceptar"
        @mouseover="moveButton"
        @click="moveButton"
        :style="{ top: buttonTop + 'px', left: buttonLeft + 'px' }"
        ref="moveableButton"
      >
        Mueve el Botón
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttonTop: 257,
      buttonLeft: 750,
      isFirstMove: true,
    };
  },
  methods: {
    moveButton() {
      // Si es la primera vez, establece la posición inicial
      if (this.isFirstMove) {
        this.isFirstMove = false;
        this.$refs.moveableButton.style.top = this.buttonTop + 'px';
        this.$refs.moveableButton.style.left = this.buttonLeft + 'px';
      } else {
        // Calcula nuevas posiciones de manera aleatoria
        const newTop = Math.floor(Math.random() * (window.innerHeight - 50)); // Resta el tamaño del botón para que no se desborde en la parte inferior
        const newLeft = Math.floor(Math.random() * (window.innerWidth - 100)); // Resta el tamaño del botón para que no se desborde en el lado derecho

        // Actualiza las posiciones en los datos del componente
        this.buttonTop = newTop;
        this.buttonLeft = newLeft;
        console.log(newLeft, newTop);
      }
    },
    btnCancelar() {
      alert("Ayrton2");
    },
  },
};
</script>

<style>
.btnAceptar {
  position: absolute; /* Asegura que la posición absoluta funcione correctamente */
}

.centered-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Esto asegura que el contenedor ocupe el 100% de la altura de la ventana */
}

button {
  margin: 0 15px; /* Margen de 15px entre los botones */
  padding: 10px 20px;
  /* Agrega otros estilos según sea necesario */
}

.btnCancelar {
  top: 257px;
}
</style>