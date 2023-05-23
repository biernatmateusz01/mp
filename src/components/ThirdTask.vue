<template>
  <div class="second-task">
    3. Wykorzystaj komponent z zadania drugiego i utwórz dwa inputy, które będą przechowywały
    wartość w zmiennych. Utwórz metodę, która po kliknięciu utworzy dwie tablice z inputów, każda
    wartość znajdująca się np. po przecinku powinna być nową wartością w tablicy, następnie metoda
    powinna przypisać do zmiennej newArray, tablice z inputa 1 bez elementów znajdujących się w
    tablicy inputa 2.Wyświetl nową tablicę jako listę.

    <div class="second-task-container">
      <div style="display: flex; margin-bottom: 12px; gap: 8px; flex-wrap: wrap">
        <InputDefault v-model="vInputFirst" placeholder="Input1" :type="'text'" />
        <InputDefault v-model="vInputSecond" placeholder="Input2" :type="'text'" />
      </div>
      <ButtonDefault @click="createArr">Create Arrays</ButtonDefault>

      <div class="elements-container">
        <ul class="list">
          <li v-for="(item, index) in newArray" :key="index" class="element" v-text="item"></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import InputDefault from '../components/InputDefault.vue'
import ButtonDefault from '../components/ButtonDefault.vue'

export default {
  data() {
    return {
      vInputFirst: '',
      vInputSecond: '',
      newArray: []
    }
  },
  methods: {
    createArr() {
      const firstInputValue = this.vInputFirst.split(',')
      const secondInputValue = this.vInputSecond.split(',')

      const firstArr = []
      const secondArr = []

      firstArr.push(firstInputValue)
      secondArr.push(secondInputValue)

      this.newArray = firstInputValue.filter((o) => secondInputValue.indexOf(o) === -1)
    }
  },
  components: {
    InputDefault,
    ButtonDefault
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
.list {
  margin-top: 12px;
}
</style>
