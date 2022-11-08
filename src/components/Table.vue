<template>
    <div class="alert alert-warning" role="alert" data-toggle="collapse" href='#collapseExample' >
        ISBN #: {{ barcode.isbnNumber }}
    </div>
    <div class="collapse" id="collapseExample">
        <div class="card card-body">
           <Result :barcode="barcode" />
        </div>
    </div>
</template>

<script>
import Result from './Result.vue'
    export default {
        name: 'Table',
        props: {
            barcode: Object
        },
        components: {
            Result,
        }
    } 
</script>
