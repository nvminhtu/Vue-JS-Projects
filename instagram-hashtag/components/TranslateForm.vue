<template>

  <div class="row" id="translateForm">
    <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
        <div class="field">
            <div class="control">
                <input class="input" type="text" v-model="textToTranslate" placeholder="Enter a Word...">
            </div>
        </div>
        <div class="field">
            <div class="control">
                <div class="select is-primary">
                <select v-model="language">
                    <option value="ru">Russian</option>
                    <option value="es">Spanish</option>
                    <option value="fr">French</option>
                    <option value="zh">Chinese</option>
                </select>
                </div>
            </div>
        </div>
        <div class="field">
            <div class="control">
                <button class="button is-link">Translate</button>
            </div>
        </div>
    </form>

  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  created() {
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>

</style>