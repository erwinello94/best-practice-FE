<template>
    <p>1. {{ barcode.firstResult }}</p>
    <p>2. {{ barcode.secondResult }}</p>
    <p>3. {{ barcode.thirdResult }}</p>
    <p>4. {{ barcode.fourthResult }}</p>
    <p>Therefore the complete ISBN is: <b>{{ barcode.fifthResult }}</b></p>
</template>

<script>
    export default {
        name: 'Result',
        props: {
            barcode: Object
        }
    } 
</script>