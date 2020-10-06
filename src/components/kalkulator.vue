<template>
    <div class="kalkulator">
        <div class="wrapper">
            <b-input-group style=" width:32em;margin-bottom:-15px; 
                            box-shadow:0 0 20px rgba(0,0,0,3);" prepend="Result">
                <b-form-input style="background-color: white;color:black;font-size:25px;text-align:right;"
                    v-model="result"></b-form-input>
            </b-input-group>
            <div class="wrapper-number">
                <div class="row">
                    <b-button variant="danger" class="number" style="width:3.9em;" @click="AC()">AC</b-button>
                    <b-button variant="warning" class="number">%</b-button>
                    <b-button pill variant="primary" class="operator" @click="bagi()">&#247;</b-button>
                </div>
                <div class="row">
                    <b-button variant="dark" class="number" @click="seven()">7</b-button>
                    <b-button variant="dark" class="number" @click="eight()">8</b-button>
                    <b-button variant="dark" class="number" style="margin-right:20px;" @click="nine()">9</b-button>
                    <b-button pill variant="primary" class="operator" @click="kali()">&#215;</b-button>
                </div>
                <div class="row">
                    <b-button variant="dark" class="number" @click="four()">4</b-button>
                    <b-button variant="dark" class="number" @click="five()">5</b-button>
                    <b-button variant="dark" class="number" style="margin-right:20px;" @click="six()">6</b-button>
                    <b-button pill variant="primary" class="operator" @click="min()">&#8722;</b-button>
                </div>
                <div class="row">
                    <b-button variant="dark" class="number" @click="one()">1</b-button>
                    <b-button variant="dark" class="number" @click="two()">2</b-button>
                    <b-button variant="dark" class="number" style="margin-right:20px;" @click="three()">3</b-button>
                    <b-button pill variant="primary" class="operator" @click="add()">&#43;</b-button>
                </div>
                <div class="row">
                    <b-button variant="dark" class="number" style="width:3.9em;" @click="zero()">0</b-button>
                    <b-button variant="warning" class="number" style="width:1.5em;">.</b-button>
                    <b-button variant="success" class="operator" @click="res()">&#61;</b-button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export let one = 1
    export let two = 2
    export let three = 3
    export let four = 4
    export let five = 5
    export let six = 6
    export let seven = 7
    export let eight = 8
    export let nine = 9
    export let zero = 0

    export let addtion = '+'
    export let subtraction = '-'
    export let multiplcation = 'x'
    export let Dividsion = '/'

    export default {
        name: "kalkulator",
        data() {
            return {
                number: {
                    one,
                    two,
                    three,
                    four,
                    five,
                    six,
                    seven,
                    eight,
                    nine,
                    zero
                },
                operator: {
                    addtion,
                    subtraction,
                    multiplcation,
                    Dividsion
                },
                oke: [],
                coba: [],
                result: 0,
                coba1: 0,
                action: ''
            }
        },
        methods: {
            hasil() {
                const res = this.oke.map((i) => String(i));
                this.result = res.join('')
            },
            hasil1() {
                const res = this.coba.map((i) => Number(i));
                this.coba1 = res.join('')
            },
            add() {
                this.oke.push(this.operator.addtion)
                this.hasil()

                this.action = "add"
                this.coba.push(this.operator.addtion)
                const x = this.coba.join('').split('+')
                if (x.length > 2) {
                    const y = Number(x[0]) + Number(x[1])
                    this.result = y
                    this.coba1 = 0
                }
            },
            min() {
                this.oke.push(this.operator.subtraction)
                this.hasil()

                this.action = 'min'
                this.coba.push(this.operator.subtraction)
                const x = this.coba.join('').split('-')
                if (x.length > 2) {
                    const y = Number(x[0]) - Number(x[1])
                    this.result = y
                    this.coba1 = 0
                }
            },
            kali() {
                this.oke.push(this.operator.multiplcation)
                this.hasil()

                this.action = 'kali'
                this.coba.push(this.operator.multiplcation)
                const x = this.coba.join('').split('*')
                if (x.length > 2) {
                    const y = Number(x[0]) * Number(x[1])
                    this.result = y
                    this.coba1 = 0
                }
            },
            bagi() {
                this.oke.push(this.operator.Dividsion)
                this.hasil()

                this.action = 'bagi'
                this.coba.push(this.operator.Dividsion)
                const x = this.coba.join('').split('/')
                if (x.length > 2) {
                    const y = Number(x[0]) / Number(x[1])
                    this.result = y
                    this.coba1 = 0
                }
            },
            one() {
                this.oke.push(this.number.one)
                this.hasil()
                this.coba.push(this.number.one)
                this.hasil1()
            },
            two() {
                this.oke.push(this.number.two)
                this.hasil()
                this.coba.push(this.number.two)
                this.hasil1()
            },
            three() {
                this.oke.push(this.number.three)
                this.hasil()
                this.coba.push(this.number.three)
                this.hasil1()
            },
            four() {
                this.oke.push(this.number.four)
                this.hasil()
                this.coba.push(this.number.four)
                this.hasil1()
            },
            five() {
                this.oke.push(this.number.five)
                this.hasil()
                this.coba.push(this.number.five)
                this.hasil1()
            },
            six() {
                this.oke.push(this.number.six)
                this.hasil()
                this.coba.push(this.number.six)
                this.hasil1()
            },
            seven() {
                this.oke.push(this.number.seven)
                this.hasil()
                this.coba.push(this.number.seven)
                this.hasil1()
            },
            eight() {
                this.oke.push(this.number.eight)
                this.hasil()
                this.coba.push(this.number.eight)
                this.hasil1()
            },
            nine() {
                this.oke.push(this.number.nine)
                this.hasil()
                this.coba.push(this.number.nine)
                this.hasil1()
            },
            zero() {
                this.oke.push(this.number.zero)
                this.hasil()
                this.coba.push(this.number.zero)
                this.hasil1()
            },
            AC() {
                this.oke = []
                this.coba = []
                this.result = 0
                this.coba1 = 0
            },
            res() {
                console.log(this.action)
                if (this.action == 'add') {
                    this.coba.push(this.operator.addtion)
                    const a = this.coba.join('').split('+')
                    if (a.length > 2) {
                        const y = Number(a[0]) + Number(a[1])
                        this.result = y
                        this.coba1 = 0
                    }
                } else if (this.action == 'min') {
                    this.coba.push(this.operator.subtraction)
                    const b = this.coba.join('').split('-')
                    if (b.length > 2) {
                        const y = Number(b[0]) - Number(b[1])
                        this.result = y
                        this.coba1 = 0
                    }
                } else if (this.action == 'kali') {
                    this.coba.push(this.operator.multiplcation)
                    const c = this.coba.join('').split('*')
                    if (c.length > 2) {
                        const y = Number(c[0]) * Number(c[1])
                        this.result = y
                        this.coba1 = 0
                    }
                } else if (this.action == 'bagi') {
                    this.coba.push(this.operator.Dividsion)
                    const x = this.coba.join('').split('/')
                    if (x.length > 2) {
                        const y = Number(x[0]) / Number(x[1])
                        this.result = y
                        this.coba1 = 0
                    }
                } else {
                    alert('hasil kosong!')
                }
            }
        }
    }
</script>

<style>
    .kalkulator {
        background-image: url('./../assets/BG (1).png');
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
    }

    .wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        flex-direction: column;
    }

    .wrapper-number {
        background-color: whitesmoke;
        width: 25em;
        display: flex;
        flex-direction: column;
        text-align: center;
        align-items: center;
        padding: 3em;
        -webkit-box-shadow: 0 0 20px rgba(0, 0, 0, 1);
        -moz-box-shadow: 0 0 20px rgba(0, 0, 0, 1);
        box-shadow: 0 0 20px rgba(0, 0, 0, 1);
    }

    .wrapper .operator {
        font-size: 25px;
        margin: 6px;
    }

    .wrapper .number {
        font-size: 28px;
        margin: 10px;
    }
</style>