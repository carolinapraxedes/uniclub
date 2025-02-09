<template>
    <div>
      <h1>Este é o Meu Componente!</h1>
      <p>Contador: {{ count }}</p>
      <button @click="incrementar">Incrementar</button>
    </div>
</template>

<script>
  export default {
    name: 'MeuComponente',
    data() {
      return {
        count: 0, // Dados reativos
      };
    },
    methods: {
      incrementar() {
        this.count++; // Método para incrementar o contador
      },
    },
  };
</script>

<style scoped>

</style>