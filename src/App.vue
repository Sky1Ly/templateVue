<script>
export default {
  name: "App",
  data() {
    return {
      texto: ""
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
          <input class="form-check-input" type="checkbox" value="" id="mostrarTexto">
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
          <label for="letra" class="form-label">Tipografía</label>
          <select class="form-select">
            <option selected>Arial</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
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
        <h1 :class="{maximaAnchura:true}">{{ texto }}</h1>
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

.maximaAnchura {
  max-width: 400px;
}

.itemCentrado {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
