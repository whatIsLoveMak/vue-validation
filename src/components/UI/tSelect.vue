<template>
  <select class="input" name="" id="modalForm">
    <option>Русский</option>
    <option>Английский</option>
    <option>Китайский</option>
    <option>Испанский</option>
  </select>
</template>

<script>
//TODO Поробуй сделать не через селект а через дивы, чтобы открывал дроп даун и стилизация, я понимаю, что ты умеешь верстать :D
// но лучше сделать всё как в макете, с ховерами
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
