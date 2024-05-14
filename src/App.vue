<script>
export default {
  name: "App",
  data() {
    return {
      texto: "",
      mostrarTexto: "",
      letras: ["Courier New", "Arial", "Georgia", "Times New Roman", "Trebuchet MS", "Verdana"],
      tipoLetra: "",
      colorFondo: "",
      colorLetra: "",
      tamaño: "",
      opacar: "",
      bordes: ""
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
          <input type="text" class="form-control" id="colorFondo" placeholder="#fff000" v-model="colorFondo">
        </div>
        <div class="mb-3">
          <label for="colorFondoTexto" class="form-label">Color de Texto - Hexadecimal</label>
          <input type="text" class="form-control" id="colorFondoTexto" placeholder="#f0f0f0" v-model="colorLetra">
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
          <label for="rango" class="form-label">Bordes</label>
          <input type="range" class="form-range" v-model="bordes" min="0" max="10" step="0.5" id="rango">
        </div>
        <div class="mb-3">
          <label for="tipografia" class="form-label">Tipografía</label>
          <select v-model="tipoLetra" class="form-select">
            <option selected value="">Seleccione un tipo de letra</option>
            <option v-for="letra in letras">{{ letra }}</option>
          </select>
        </div>
        <div class="form-check mb-3">
          <input class="form-check-input" type="checkbox" id="opacidad" v-model="opacar">
          <label class="form-check-label" for="opacidad">¿Opaco?</label>
        </div>
        <div class="mb-3">
          <label class="form-label">Tamaño de letra</label>
          <br />
          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraPeque" value="1.9rem" v-model="tamaño">
            <label class="form-check-label" for="tamañoLetraPeque">Pequeño</label>
          </div>

          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraMed" value="2.5rem" v-model="tamaño">
            <label class="form-check-label" for="tamañoLetraMed">Mediano</label>
          </div>

          <div class="form-check form-check-inline">
            <input class="form-check-input" type="radio" name="tamañoLetra" id="tamañoLetraGrande" value="3.1rem" v-model="tamaño">
            <label class="form-check-label" for="tamañoLetraGrande">Grande</label>
          </div>
        </div>
      </div>

      <!--Render-->
      <div class="col-sm-6 itemCentrado">
        <h1 :class="{
          caja: true,
          condicionales: opacar
        }" :style="{
          fontFamily: tipoLetra,
          backgroundColor: colorFondo,
          color: colorLetra,
          fontSize: tamaño,
          borderRadius: bordes + '%'
        }" v-show="mostrarTexto">{{ texto }}</h1>
      </div>
    </div>
  </div>
</template>

<style>
.caja {
  width: 400px;
  height: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: auto;
}

.condicionales {
  opacity: 0.5;
}

.itemCentrado {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
