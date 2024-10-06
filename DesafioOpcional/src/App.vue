<template>
  <div id="app" class="container">
    <div class="formulario">
      <h2>Formulario de Evaluación</h2>
      <form @submit.prevent="handleSubmit">
        <!-- Título (Input) -->
        <div class="form-group">
          <label for="titulo">Título:</label>
          <input type="text" id="titulo" v-model="form.titulo" />
        </div>

        <!-- Emoji (Select) -->
        <div class="form-group">
          <label for="emoji">Emoji:</label>
          <select id="emoji" v-model="form.emoji">
            <option value="">Seleccione un emoji</option>
            <option>😊</option>
            <option>😢</option>
            <option>😡</option>
            <option>😍</option>
          </select>
        </div>

        <!-- Apreciación (Radio) -->
        <div class="form-group">
          <label>Apreciación:</label>
          <div>
            <input type="radio" id="aprec_buena" value="Buena" v-model="form.apreciacion" />
            <label for="aprec_buena">Buena</label>
          </div>
          <div>
            <input type="radio" id="aprec_regular" value="Regular" v-model="form.apreciacion" />
            <label for="aprec_regular">Regular</label>
          </div>
          <div>
            <input type="radio" id="aprec_mala" value="Mala" v-model="form.apreciacion" />
            <label for="aprec_mala">Mala</label>
          </div>
        </div>

        <!-- Competencias (Checkbox) -->
        <div class="form-group">
          <label>Competencias:</label>
          <div>
            <input type="checkbox" id="competencia_componentes" value="Morfologia de un componente" v-model="form.competencias" />
            <label for="competencia_componentes">morfologia de un componente</label>
          </div>
          <div>
            <input type="checkbox" id="competencia_One" value="One way y two way" v-model="form.competencias" />
            <label for="competencia_One">One way y two way data binding</label>
          </div>
          <div>
            <input type="checkbox" id="competencia_Patron" value="Patron diseño MVVM" v-model="form.competencias" />
            <label for="competencia_Patron">Patron diseño MVVM</label>
          </div>
        </div>
        <div>
        <input type="checkbox" id="competencia_estado" value="Estado" v-model="form.competencias" />
            <label for="competencia_estado">Estado </label>
          
        </div>
        <div>
        <input type="checkbox" id="competencia_Directivas" value="Directivas" v-model="form.competencias" />
            <label for="competencia_Directivas">Directivas</label>
          
        </div>

        <!-- Opinión (Textarea) -->
        <div class="form-group">
          <label for="opinion">Opinión:</label>
          <textarea id="opinion" v-model="form.opinion"></textarea>
        </div>
      </form>
    </div>

    <!-- Interpolación de los datos ingresados -->
    <div class="resultados">
      <h2>Resumen</h2>
      <p><strong>Título:</strong> {{ form.titulo }}</p>
      <p><strong>Emoji:</strong> {{ form.emoji }}</p>
      <p><strong>Apreciación:</strong> {{ form.apreciacion }}</p>
      <p><strong>Competencias:</strong> {{ form.competencias.join(', ') }}</p>
      <p><strong>Opinión:</strong> {{ form.opinion }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        titulo: '',
        emoji: '',
        apreciacion: '',
        competencias: [],
        opinion: ''
      },
      submitted: false
    };
  },
  methods: {
    handleSubmit() {
      this.submitted = true;
      // Aquí puedes procesar los datos, como enviarlos a una API.
      console.log('Formulario enviado:', this.form);
    }
  }
};
</script>

<style >
#app {
  display: contents;
}
.container {
  display: flex;
  justify-content: space-between;
  padding: 50%;
}

.formulario, .resultados {
  width: 45%;
}

form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input[type="text"], select, textarea {
  width: 100%;
  padding: 8px;
}

textarea {
  height: 100px;
}


.resultados {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
}

h2 {
  color: #42b983;
}
</style>





  