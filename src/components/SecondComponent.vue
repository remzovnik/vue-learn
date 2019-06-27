<template>
    <div class="component">
        <h1>Это второй компонент</h1>
        <button type="button" @click="handleClick(true)">Увидеть первый компонент</button>
    </div>
</template>

<script>
export default {
  name: 'second-component',
  props: {
    handleClick: Function,
  },
};
</script>

<style scoped>
.component {
  position: absolute;
  top: 100px;
  right: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: -20px;
}
</style>
