<template>
  <h1 class="text-4xl font-bold mb-8 text-white">Calculadora</h1>
  <div class="flex flex-col items-center justify-center min-h-auto rounded-lg bg-gray-900">
    <div class="bg-gray-800 p-6 rounded-lg shadow-lg">
      <div class="mb-4">
        <input
          class="w-full bg-gray-700 text-white text-right text-2xl p-4 rounded mb-4"
          type="text"
          v-model="result"
        />
      </div>
      <div class="grid grid-cols-4 gap-2">
        <input
          type="button"
          v-model="num.sete"
          @click="concatenar('sete')"
          @keyup.7="concatenar('sete')"
          value="7"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.oito"
          @click="concatenar('oito')"
          @keyup.8="concatenar('oito')"
          value="8"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.nove"
          @click="concatenar('nove')"
          @keyup.9="concatenar('nove')"
          value="9"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          @click="operar('sum')" 
          value="+" 
          class="bg-orange-500 hover:bg-orange-400 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.quatro"
          @click="concatenar('quatro')"
          @keyup.4="concatenar('quatro')"
          value="4"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.cinco"
          @click="concatenar('cinco')"
          @keyup.5="concatenar('cinco')"
          value="5"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.seis"
          @click="concatenar('seis')"
          @keyup.6="concatenar('seis')"
          value="6"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          @click="operar('subtract')" 
          value="-" 
          class="bg-orange-500 hover:bg-orange-400 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.um"
          @click="concatenar('um')"
          @keyup.1="concatenar('um')"
          value="1"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.dois"
          @click="concatenar('dois')"
          @keyup.2="concatenar('dois')"
          value="2"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input
          type="button"
          v-model="num.tres"
          @click="concatenar('tres')"
          @keyup.3="concatenar('tres')"
          value="3"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          @click="operar('multiply')" 
          value="*" 
          class="bg-orange-500 hover:bg-orange-400 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          v-model="num.zero" 
          @click="concatenar('zero')" 
          @keyup.0="concatenar('zero')"
          value="0"
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded col-span-2"
        />
        <input 
          type="button" 
          @click="operar('ponto')" 
          @keyup.period="operar('ponto')"
          value="." 
          class="bg-gray-600 hover:bg-gray-500 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          @click="operar('divide')" 
          @keyup.slash="operar('divide')"
          value="/" 
          class="bg-orange-500 hover:bg-orange-400 text-white font-bold py-4 px-6 rounded"
        />
        <input 
          type="button" 
          @click="calcular" 
          @keyup.enter="calcular"
          value="=" 
          class="bg-green-500 hover:bg-green-400 text-white font-bold py-4 px-6 rounded col-span-2"
        />
        <input 
          type="button" 
          @click="zerar" 
          @keyup.backspace="zerar"
          value="C" 
          class="bg-red-500 hover:bg-red-400 text-white font-bold py-4 px-6 rounded col-span-2"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      num: {
        um: "1",
        dois: "2",
        tres: "3",
        quatro: "4",
        cinco: "5",
        seis: "6",
        sete: "7",
        oito: "8",
        nove: "9",
        zero: "0",
      },
      operador: {
        sum: " + ",
        subtract: " - ",
        multiply: " * ",
        divide: " / ",
        ponto: ".",
      },
      result: "",
      igual: "=",
      limpar: "C",
    };
  },
  methods: {
    concatenar(num) {
      this.result = this.result + this.num[num];
    },
    operar(operador) {
      this.result = this.result + this.operador[operador];
    },
    calcular() {
      try {
        this.result = eval(this.result);
      } catch (error) {
        this.result = "Erro";
      }
    },
    zerar() {
      this.result = "";
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
