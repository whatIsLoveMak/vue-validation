<template>
  <select class="input" name="" id="modalForm">
    <option>Русский</option>
    <option>Английский</option>
    <option>Китайский</option>
    <option>Испанский</option>
  </select>
</template>

<script>
export default {
  name: "tSelect",
};
</script>

<style scoped>
select {
  width: 100%;
  padding: 16px 16px;
  border: 1px solid #DBE2EA;
  transition: all 0.4s ease;
  margin-bottom: 34px;
  border-radius: 6px;
  box-sizing: border-box;
}
</style>
