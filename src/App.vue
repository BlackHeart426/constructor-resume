<template>
  <div class="container column">
    <app-menu @add-block="handlerAddBlock"/>
    <app-content :content="content"/>
  </div>
  <app-comment/>
</template>

<script>
import AppComment from "@/components/AppComment";
import AppContent from "@/components/AppContent";
import AppMenu from "@/components/AppMenu";

export default {
  components: {
    AppComment,
    AppContent,
    AppMenu,
  },
  data() {
    return {
      content: [],
    }
  },
  methods: {
    /**
     * действие по добавлению нового блока в массив
     * @param name
     * @param value
     */
    handlerAddBlock(name, value) {
      this.content.push({nameComponent: name, value})
    }
  }
}
</script>

<style>

</style>
