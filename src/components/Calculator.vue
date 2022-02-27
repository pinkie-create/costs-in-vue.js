<template>
  <div>
    <div class="display">
      <h1>Calculator</h1>
      <label for="operand1">
        <input type="number" id="operand1" v-model.number="operand1" />
      </label>
      <label for="operand2">
        <input type="number" id="operand2" v-model.number="operand2" />
      </label>
      <span>{{ result }}</span>
    </div>
    <div class="keyboard">
      <button @click="sum">+</button>
      <button @click="sub">-</button>
      <button @click="multi">*</button>
      <button @click="div">/</button>
      <button @click="pow">Возведение в степень</button>
      <button @click="divInt">Целочисленное деление</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  props: {},
  data: () => ({
    operand1: 0,
    operand2: 0,
    result: 0,
    msg: "Calculator",
  }),
  methods: {
    sum() {
      this.result = this.operand1 + this.operand2;
    },
    sub() {
      this.result = this.operand1 - this.operand2;
    },
    multi() {
      this.result = this.operand1 * this.operand2;
    },
    div() {
      this.result = this.operand1 / this.operand2;
    },
    pow() {
      this.result = Math.pow(this.operand1, this.operand2);
    },
    divInt() {
      if (this.operand1 / this.operand2 >= 0)
        return (this.result = Math.floor(this.operand1 / this.operand2));
      else return (this.result = Math.ceil(this.operand1 / this.operand2));
    },
  },
};
</script>
