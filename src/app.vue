<template>
  <div id="calculator">
    <header>
      <h1>Calculator</h1>
    </header>
    <section class="calculator" id="calculator">
      <calculator></calculator>
    </section>
    <footer>
      <span class="author">
      <pre>
        Created by Zeks
         October, 2018
      </pre>
      </span>
    </footer>
  </div>

</template>

<script>
import Calculator from 'components/Calculator.vue'
export default {
  name: 'app',
  components: {
    Calculator
  }
 }

</script>

