<script setup>
import Header from './components/Header.vue'
import Form from './components/Form.vue'
import Table from './components/Table.vue'
import Result from './components/Result.vue'
import Barcodes from './components/Barcodes.vue'
</script>

<script>
export default {
  name: 'App',
  components: {
    Header,
    Form,
    Table,
    Result,
    Barcodes
  },

  data(){
    return {
      barcodes: []
    }
  },

  methods: {

    toggleResult(){
       this.showResult = !this.showResult
    },

    addBarcode(barcode){
      this.barcodes = [...this.barcodes, barcode]
    }
  },

}
</script>

<template>
  <div class="container">
        <Header />
        <Form @add-barcode="addBarcode"/>
        <Barcodes :barcodes="barcodes"/>
  </div>
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
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
