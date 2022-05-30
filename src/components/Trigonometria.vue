<template>
    <div class="container">
        <div class="row">
            <h1 class="text-center">Teorema de Pitágoras</h1>
            <hr/>
            <div class="col-sm-4">
                <div class="form-group">
                    <label for="cat-op">Cateto Oposto:</label>
                    <input type="number" step="0.01" min="0" id="cat-op" name="cat-op" class="form-control" placeholder="Cateto Oposto" v-model="catOp" @keyup="calc()">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="cat-ad">Cateto Adjacente:</label>
                    <input type="number" step="0.01" min="0" id="cat-ad" name="cat-ad" class="form-control" placeholder="Cateto Adjacente" v-model="catAd" @keyup="calc()">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="hip">Hipotenusa:</label>
                    <input type="number" step="0.01" min="0" id="hip" name="hip" class="form-control" placeholder="Hipotenusa" v-model="hip" disabled="disabled">
                </div>
            </div>
        </div>
        
        <div class="row margin-top">
            <h1 class="text-center">Razões Trigonométricas</h1>
            <hr/>
            <div class="col-sm-4">
                <div class="form-group">
                    <label for="sen">Seno (Sen):</label>
                    <input type="number" step="0.01" min="0" id="sen" name="sen" class="form-control" placeholder="Seno" v-model="sen" disabled="disabled">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="cos">Cosseno (Cos):</label>
                    <input type="number" step="0.01" min="0" id="cos" name="cos" class="form-control" placeholder="Cosseno" v-model="cos" disabled="disabled">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="tan">Tangente (Tan/Tg):</label>
                    <input type="number" step="0.01" min="0" id="tan" name="tan" class="form-control" placeholder="Tangente" v-model="tan" disabled="disabled">
                </div>
            </div>
        </div>

        <div class="row">
            <div class="col-sm-4">
                <div class="form-group">
                    <label for="sec">Secante (Sec):</label>
                    <input type="number" step="0.01" min="0" id="sec" name="sec" class="form-control" placeholder="Secante" v-model="sec" disabled="disabled">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="cossec">Cossecante (Cossec):</label>
                    <input type="number" step="0.01" min="0" id="cossec" name="cossec" class="form-control" placeholder="Cossecante" v-model="cossec" disabled="disabled">
                </div>
            </div>

            <div class="col-sm-4">
                <div class="form-group">
                    <label for="cotan">Cotangente (Cotan/Cotg):</label>
                    <input type="number" step="0.01" min="0" id="cotan" name="cotan" class="form-control" placeholder="Cotangente" v-model="cotan" disabled="disabled">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                catOp: null,
                catAd: null,
                hip: null,
                sen: null,
                cos: null,
                tan: null,
                sec: null,
                cossec: null,
                cotan: null
            }
        },

        methods: {
            calc() {
                if ((!isNaN(this.catOp) && this.catOp != null) && (!isNaN(this.catAd) && this.catAd != null)) {
                    let hip = Math.sqrt(Math.pow(this.catOp, 2) + Math.pow(this.catAd, 2));

                    this.hip = hip;
                    this.sen = this.catOp / this.hip;
                    this.cos = this.catAd / this.hip;
                    this.tan = this.sen / this.cos;
                    this.sec = 1 / this.cos;
                    this.cossec = 1 / this.sen;
                    this.cotan = 1 / this.tan;
                }
            }
        }
    }
</script>

<style scoped>
    .margin-top {
        margin-top: 50px;
    }
</style>
