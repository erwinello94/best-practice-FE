<script setup>
import Header from './components/Header.vue'
import Form from './components/Form.vue'
import Result from './components/Result.vue'
import Barcodes from './components/Barcodes.vue'
</script>

<script>
export default {
  name: 'App',
  components: {
    Header,
    Form,
    Result,
    Barcodes
  },

  data(){
    return {
      barcodes: []
    }
  },

  methods: {
    addBarcode(barcode){
      this.barcodes = [...this.barcodes, barcode]
    }
  },

  // created() {
  //   this.barcodes = [
  //     {
  //       firstResult: '(9 x 1)(7 x 3)(8 x 1)(0 x 3)(1 x 1)(4 x 3)(3 x 1)(0 x 3)(0 x 1)(7 x 3)(2 x 1)(3 x 3)',
  //       secondResult: '86'
  //     }
  //   ]
  // }
}
</script>

<template>
  <div class="container1">
        <Header />
        <Form @add-barcode="addBarcode"/>
        <Barcodes :barcodes="barcodes"/>
  </div>
</template>

<style scoped>
/* 
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
 */

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container1 {
  max-width: 800px;
  margin: 50px auto;
  overflow: auto;
  min-height: 500px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 3px;
  /* position: relative; */
}

</style>
