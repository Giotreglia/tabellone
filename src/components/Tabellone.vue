<script>
export default {
    name: 'Tabellone',
    data() {
        return {
            inputNumero: '',
            numeroPrincipale: []
        }
    },
    methods: {
        addNumber() {
            this.numeroPrincipale.push(this.inputNumero);
            this.inputNumero = '';
        }
    },
}
</script>

<template>
    <div id="header-container" class="d-flex justify-content-center align-items-center p-4">
        <img src="../../public/logo-frattimi.png" alt="">
        <div>
            <h1 class="title mb-0">Baffest 2023</h1>
            <h5 class="fs-4">by I Frattimi</h5>
        </div>
    </div>
    <div class="d-flex flex-column justify-content-between px-3">
        <h1 class="text text-center mt-2">Stiamo servendo il numero</h1>
        <h1 id="numero-principale" class="text-center">{{ numeroPrincipale[numeroPrincipale.length - 1] }}</h1>

        <h1 class="text text-center text-light m-3">Ultimi numeri chiamati</h1>
        <div class="number-container">
            <div class="number-wrapper text-light fs-5 d-flex justify-content-center p-5" v-for="(item, i) in 4" :key="i">
                <h1 class="numero-secondario">{{ numeroPrincipale[(numeroPrincipale.length - 1) - (i + 1)] }}</h1>
            </div>
        </div>
    </div>

    <div>
        <input type="text" @keyup.enter="this.addNumber()" v-model="inputNumero">
    </div>
</template>

<style>
#header-container {
    background-color: lightgrey;
}

#numero-principale {
    color: greenyellow;
    font-size: 400px;
    line-height: 400px;
}

.numero-secondario {
    color: greenyellow;
    font-size: 80px;
}

.text {
    color: white;
    font-size: 50px;
}

.title {
    font-size: 100px;
}

.number-container {
    display: flex;

}

.number-wrapper {
    width: calc(100% / 4);
    border: solid 3px white;
}

img {
    height: 200px;
    width: 260px;
    margin-top: 10px;
}

input {
    position: absolute;
    bottom: 0;
    right: 0;
    background-color: #1a1a1a;
    border: solid 1px white;
}
</style>