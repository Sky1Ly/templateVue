<script>
export default {
  name: "App",
  data() {
    return {
      texto: "",
      mostrarTexto: "",
      tipoLetra: "https://developer.mozilla.org/es/docs/Learn/CSS/Styling_text/Fundamentals#tipos_de_letra"
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="row">
      <!--Formulario-->
      <div class="col-sm-6 bg-success rounded text-light">
        <div class="mb-3">
          <label for="colorFondo" class="form-label">Color de Fondo - Hexadecimal</label>
          <input type="text" class="form-control" id="colorFondo" placeholder="#fff000">
        </div>
        <div class="mb-3">
          <label for="colorFondoTexto" class="form-label">Color de Texto - Hexadecimal</label>
          <input type="text" class="form-control" id="colorFondoTexto" placeholder="#f0f0f0">
        </div>
        <div class="form-check mb-3">
          <input class="form-check-input" type="checkbox" value="" id="mostrarTexto" v-model="mostrarTexto">
          <label class="form-check-label" for="mostrarTexto">¿Mostrar Texto?</label>
        </div>
        <div class="mb-3">
          <label for="textoAMostrar" class="form-label">Contenido Textual</label>
          <textarea v-model="texto" class="form-control" id="textoAMostrar" rows="2"></textarea>
        </div>
        <div class="mb-3">
          <label for="rango" class="form-label">Borde</label>
          <input type="range" class="form-range" min="0" max="10" step="0.5" id="rango">
        </div>
        <div class="mb-3">
          <label for="tipografia" class="form-label">Tipografía</label>
          <select v-model="tipoLetra" class="form-select">
            <option selected value="">Seleccione un tipo de letra</option>
            <option value="1">Times New Roman</option>
            <option value="2">Georgia</option>
            <option value="3">Palatino</option>
          </select>
        </div>
        <div class="form-check mb-3">
          <input class="form-check-input" type="checkbox" value="" id="opacidad">
          <label class="form-check-label" for="opacidad">¿Opaco?</label>
        </div>
        <div class="mb-3">
          <label class="form-label">Tamaño de letra</label>
          <br />
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraPeque">
            <label class="form-check-label" for="tamañoLetraPeque">Pequeño</label>
          </div>

          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraMed">
            <label class="form-check-label" for="tamañoLetraMed">Mediano</label>
          </div>

          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraGrande">
            <label class="form-check-label" for="tamañoLetraGrande">Grande</label>
          </div>
        </div>
      </div>

      <!--Render-->
      <div class="col-sm-6">
        <div :class="{
          caja: true,
          itemCentrado: true
        }">
          <h1 :style="{fontFamily: tipoLetra}" v-show="mostrarTexto">{{ texto }}</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.caja {
  width: 400px;
  height: 400px;
  background-Color: red;
}

.itemCentrado {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
