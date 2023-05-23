<template>
  <div class="second-task">
    2. Utwórz komponent (input), który będzie obsługiwał two-way data binding (zmienna przekazywana
    przez v-model - od rodzica). Wyświetl tą zmienną w rodzicu
    <div class="second-task-container">
      <div style="display: flex">
        <InputDefault placeholder="wpisz swoje imie" :type="'text'" v-model="vName" />
      </div>
      <p class="vmodel-text">Name: <span v-text="vName"></span></p>
    </div>
  </div>
</template>

<script>
import InputDefault from '../components/InputDefault.vue'
export default {
  emits: {
    getModelValue: null
  },
  data() {
    return {
      vName: ''
    }
  },
  components: {
    InputDefault
  }
}
</script>

<style scoped>
.wrapper {
  max-width: 1600px;
  display: block;
  margin: auto;
  padding: 24px;
}
.second-task {
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.first-task-container {
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.square {
  background: rgb(28, 28, 224);
  height: 120px;
  width: 120px;
}
.vmodel-text {
  font-size: 14px;
  margin-top: 12px;
}
</style>
