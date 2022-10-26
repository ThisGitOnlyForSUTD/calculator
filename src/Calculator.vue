<template>
    <section class="calculator" id="calculator">
      <calculator-content></calculator-content>
    </section>
</template>

<script>
import CalculatorContent from 'components/CalculatorContent.vue'
export default {
  name: 'calculator',
  components: {
    CalculatorContent
  }
 }

</script>

<style>
html{
   font-size:62.5%;
}

body{
  font-family: 'Geometria';
  font-weight: 400;
  background: linear-gradient(122.76deg, #FFA2A2 4.09%, #FF7B7B 91.04%);
}

.calculator{
  margin: 0 auto;
  text-align: center;
  padding: 5px;
  width: 100%;
  max-width: 480px;
  height: 800px;
  background: linear-gradient(155.23deg, #28518E 0%, #3A77D1 100%);
  border-radius: 18px;
}
</style>
