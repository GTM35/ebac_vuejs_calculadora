<script setup>
import { reactive } from "vue";

const estado = reactive({
  number1: "",
  number2: "",
  operator: "",
  result: "",
});

const calculate = () => {
  const { number1, number2, operator } = estado;

  if (number1 != "" && number2 != "" && operator != "") {
    switch (operator) {
      case "min":
        estado.result = number1 - number2;
        break;
      case "sum":
        estado.result = number1 + number2;
        break;
      case "mult":
        estado.result = number1 * number2;
        break;
      case "div":
        estado.result = number1 / number2;
        break;
      case "mod":
        estado.result = number1 % number2;
        break;
    }
  }
};

const clear = () => {
  estado.result = "";
  estado.number1 = "";
  estado.number2 = "";
};
</script>

<template>
  <div class="container p-5 m-auto">
    <div class="display p-5 rounded-4 bg-dark">
      <form class="d-flex justify-content-center gap-5">
        <input
          type="number"
          class="form-control"
          min="0"
          v-model="estado.number1"
          @change="calculate()"
        />

        <select
          id="operators"
          class="form-select"
          v-model="estado.operator"
          @change="calculate()"
        >
          <option value="min">-</option>
          <option selected value="sum">+</option>
          <option value="mult">*</option>
          <option value="div">/</option>
          <option value="mod">%</option>
        </select>
        <input
          type="number"
          class="form-control"
          min="0"
          v-model="estado.number2"
          @change="calculate()"
        />
      </form>
      <div
        class="result d-flex justify-content-center flex-column align-items-center mt-5 text-light gap-2 h5"
      >
        <span>Resultado</span>
        <p class="result-text">{{ estado.result }}</p>
      </div>

      <div class="button d-flex justify-content-center mt-5">
        <button class="btn btn-primary btn-lg" @click="clear()">Limpar</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.display {
  background-color: #ddd;
}
</style>
