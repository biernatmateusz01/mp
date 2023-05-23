<template>
  <div class="first-task">
    1. Utwórz komponent (przycisk), który po kliknięciu wyświetli niebieski kwadrat, a po
    ponownym kliknięciu ukryje kwadrat.
    <div class="first-task-container">
      <div>
        <button-default @click="showSquare">show square</button-default>
      </div>
      <Transition name="fade">
        <div v-show="isSquare" class="square"></div>
      </Transition>
    </div>
  </div>
</template>

<script>
import ButtonDefault from '../components/ButtonDefault.vue'
export default {
  data() {
    return {
      isSquare: false
    }
  },
  components: {
    ButtonDefault
  },
  methods:{
    showSquare(){
      this.isSquare = !this.isSquare
    }
  }
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.wrapper {
  max-width: 1600px;
  display: block;
  margin: auto;
  padding: 24px;
}
.first-task {
  display: flex;
  flex-direction: column;
}
.first-task-container {
  margin-top: 12px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.square {
  background: rgb(28, 28, 224);
  height: 120px;
  width: 120px;
}
</style>
