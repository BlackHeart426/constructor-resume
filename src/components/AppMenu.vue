<template>
  <form class="card card-w30">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="typeBlock">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3" v-model="valueBlock"></textarea>
    </div>

    <button class="btn primary" :disabled="isDisable" @click.prevent="onAddBlock">Добавить</button>
  </form>
</template>

<script>
export default {
  emits: ['add-block'],
  name: "AppMenu",
  data() {
    return {
      typeBlock: 'title',
      valueBlock: ''
    }
  },
  computed: {
    /**
     * Проверка на блокировку кнопки
     **/
    isDisable() {
      return this.valueBlock.length === 0
    }
  },
  methods: {

    /**
     * Событие по вызову эмита
     */
    onAddBlock() {
      this.$emit('add-block', 'app-' + this.typeBlock, this.valueBlock )
      this.typeBlock = 'title'
      this.valueBlock = ''
    }
  }

}
</script>

<style scoped>

</style>