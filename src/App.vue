<script setup>
import {reactive, computed} from 'vue';
    const estado = reactive({
      opcaoSelecionada: 'adicao',
      numero1: '',
      numero2: '',      
    })

    const resultado = computed(() => {
      const valor1 = Number(estado.numero1)
      const valor2 = Number(estado.numero2)

      switch (estado.opcaoSelecionada) {
        case 'adicao':
          return valor1 + valor2;
        case 'subtracao':
          return valor1 - valor2;
        case 'multiplicacao':
          return valor1 * valor2;
        case 'divisao':
          return valor1 / valor2;

        default:
          return 
      }

    })
</script>

<template>
  <div class="container">
    <h1 class="text-center mt-5">Calculadora aritmética</h1>
    <form>
      <div class="form-group d-flex justify-content-center align-items-center">
        <input type="number" class="form-control me-3" placeholder="Informe um valor númerico" v-model="estado.numero1">

        <select v-model="estado.opcaoSelecionada" class="form-select text-center me-3 lead">
          <option value="adicao">Adição +</option>
          <option value="subtracao">Subtração -</option>
          <option value="multiplicacao">Multiplicação *</option>
          <option value="divisao">Divisão %</option>
          
        </select>
        <input type="number" class="form-control" placeholder="Informe um valor númerico" v-model="estado.numero2">
      </div>
    </form>
    <ul class="list-group d-flex justify-content-end align-items-end mt-3">
        <li class="list-group-item col-md-4 d-flex justify-content-between align-items-center">
           {{ resultado }}<i class="bi bi-calculator lead"></i>
        </li>
      </ul>
  </div>
</template>

<style scoped></style>
