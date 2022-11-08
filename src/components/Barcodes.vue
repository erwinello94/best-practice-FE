<template>
    <div v-for="barcode in barcodes">
        <Table :barcode="barcode" />
    </div>
</template>
<script>
import Table from './Table.vue'
    export default {
        name: 'Barcodes',
        props: {
            barcodes: Array
        },
        components: {
            Table
        }
    }
</script>