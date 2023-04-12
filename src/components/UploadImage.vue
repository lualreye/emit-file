<script setup>
const emit = defineEmits(['pass-image']);

function onFileChange(event) {
  const file = event.target.files[0];
  emit('pass-image', file)
}

</script>

<template>
  <div class="input-wrapper">
    <input
      type="file"
      class="input"
      accept="image/*"
      @change="onFileChange">
    <div class="fake-input">
      Subir archivo
    </div>
  </div>
</template>

<style scoped>
.input-wrapper {
  width: 120px;
  padding: 4px 8px;
  position: relative;
  margin: auto;
}
.input {
  opacity: 0;
  cursor: pointer;
}
.fake-input {
  width: 100%;
  height: 100%;
  border-radius: 4px;
  background-color: #41b883;
  color: white;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  pointer-events: none;
}
</style>