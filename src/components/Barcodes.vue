<template>
    <div v-for="barcode in barcodes">
        <Result :barcode="barcode" />
    </div>
</template>

<script>
import Result from './Result.vue'
    export default {
        name: 'Barcodes',
        props: {
            barcodes: Array
        },
        components: {
            Result,
        }
    }
</script>