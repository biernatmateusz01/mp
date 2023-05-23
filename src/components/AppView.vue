<template>
  <div class="wrapper">
    <FirstTask />
    <SecondTask />
    <ThirdTask />
  </div>
</template>

<script>
import FirstTask from '../components/FirstTask.vue'
import SecondTask from '../components/SecondTask.vue'
import ThirdTask from '../components/ThirdTask.vue'

export default {
  components: {
    FirstTask,
    SecondTask,
    ThirdTask
  }
}
</script>

<style scoped>
.wrapper {
  max-width: 1600px;
  display: block;
  margin: auto;
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}
</style>
