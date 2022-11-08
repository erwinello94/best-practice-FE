<template>
    <form @submit="onSubmit">
        <div class="row">
            <div class="col-sm-10">
                <input type="text" v-model="isbn_number" class="form-control" id="inlineFormInput" placeholder="ISBN barcode number">
            </div>
            <div class="col-sm-2">
            <button type="submit" class="btn btn-outline-warning">Calculate</button>
            </div>
        </div>
    </form>
</template>

<script>
    export default {
        name: 'Form',
        data(){
            return {
                isbn_number: ''
            }
        },
        methods: {
            onSubmit(e){
                e.preventDefault()
                if(isNaN(this.isbn_number)){
                    alert("ISBN number is not applicable for any characters!")
                    return
                }

                if(this.isbn_number.length > 12 || this.isbn_number.length < 12 ){
                    alert("Only 12 length applicable numbers!")
                    return
                }

                var number = this.isbn_number
                var multiply = 0, sum = 0
                var str = '', strArray = ''
                for (let i = 0; i < number.length; i++) {
                    if (i % 2 == 0) {
                        multiply = number[i] * 1
                        strArray = '(' + number[i] +' x 1)'
                    } else if (i % 2 == 1) {
                        multiply = number[i] * 3
                        strArray = '(' + number[i] +' x 3)'
                    }
                    str += strArray
                    sum += multiply
                }
                var remainder = sum % 10
                var thirdRes = '' + sum + ' mod 10 = ' + remainder
                var subFourthRes = 10 - remainder
                var fourthRes = '10 - '+ remainder+ ' = ' + subFourthRes
                const newBarcode = {
                    firstResult: str,
                    secondResult: sum,
                    thirdResult: thirdRes,
                    fourthResult: fourthRes,
                    fifthResult: this.isbn_number + subFourthRes
                }
                console.log(newBarcode)
                this.$emit('add-barcode', newBarcode)
                this.isbn_number = '' 
            }
        }
    }
</script>

<style>
</style>