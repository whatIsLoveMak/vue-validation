<template>
<div class="checkbox-row" >
  <label>Принимаю <span> <a href="#">условия </a> </span>использования</label>
  <input type="checkbox" id="modalForm">
</div>
</template>

<script>

export default {
  name: "tCheckbox",
}
</script>

<style scoped>
.checkbox-row {
  display: flex;
  flex-direction: row-reverse;
  justify-content: flex-end;
  align-items: center;
  margin-bottom: 40px;
  color: black;
}
a {
  color: #0880AE;
  text-decoration: none;
}
input {
  border: 1px solid #0880AE;
}
</style>