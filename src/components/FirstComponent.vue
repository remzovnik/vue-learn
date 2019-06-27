<template>
    <div class="component">
        <h1>Это первый компонент</h1>
        <button type="button" @click="handleClick(false)">Увидеть второй компонент</button>
    </div>
</template>

<script>
export default {
  name: 'first-component',
  props: {
    handleClick: Function,
  },
};
</script>

<style scoped>
.component {
  position: absolute;
  top: 100px;
  left: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: -20px;
}
</style>