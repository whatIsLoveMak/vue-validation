<template>
  <label>
    <span>{{ item.labelInner }}</span>
    <input @blur="sendType" @input="input" :type="item.type" :placeholder="item.placeholder" :id="item.type" :class="item.className" :form="item.id" />
    <span v-if="toggleError" class="error">{{item.error}}</span>
  </label>
</template>

<script>
export default {
  name: "tInput",
  props: {
    item: {
      type: Object,
      default: () => {
        return {}
      },
    },
    value: {
      type: [String, Number],
      default: '',
    },
    check: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      obj: this.item,
      inputValue: this.item,
    }
  },
  methods: {
    input(event) {
      let value = event.target.value
      this.$emit('input', value)
    },
    sendType(){
      this.$emit('get-type',this.obj)
    },
    toggleError(){
      this.check
    }
  },
};
</script>

<style scoped>
label {
  margin-bottom: 7px;
}
input {
  width: 100%;
  padding: 16px 16px;
  border: 1px solid #DBE2EA;
  transition: all 0.4s ease;
  margin-bottom: 34px;
  border-radius: 6px;
  box-sizing: border-box;
}
input::placeholder {
  color: #7C9CBF;
}
input:focus {
  border: 2px solid #0880AE;
}
</style>
