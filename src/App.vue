<script setup></script>

<template>
  <div class="container p-5 m-auto">
    <div class="display p-5 rounded-4 bg-dark">
      <form class="d-flex justify-content-center gap-5">
        <input type="number" class="form-control" />
        <select id="operators" class="form-select">
          <option value="subtracao">-</option>
          <option selected value="adicao">+</option>
          <option value="multiplicacao">*</option>
          <option value="divisao">/</option>
          <option value="mod">%</option>
        </select>
        <input type="number" class="form-control" />
      </form>
      <div
        class="result d-flex justify-content-center flex-column align-items-center mt-5 text-light gap-2 h5"
      >
        <span>Resultado</span>
        <p class="result-text">10</p>
      </div>

      <div class="button d-flex justify-content-center mt-5">
        <button class="btn btn-primary btn-lg">Limpar</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.display {
  background-color: #ddd;
}
</style>
