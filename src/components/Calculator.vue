<template>
    <div class="cal-border">
        <div class="cal-display">
            <div class="cal-formula" v-cloak>{{ formula }}</div>
            <div class="cal-result" v-cloak>{{ result }}</div>
        </div>
        <div class="cal-items">
            <div class="cal-row-1">
                <div class="cal-item" @click="back()">←</div>
                <div class="cal-item" @click="cleanRes()">CE</div>
                <div class="cal-item" @click="clean()">C</div>
                <div class="cal-item" @click="place('+')">+</div>
                <div class="cal-item" @click="squareroot()">√</div>
            </div>
            <div class="cal-row-2">
                <div class="cal-item" @click="place(7)">7</div>
                <div class="cal-item" @click="place(8)">8</div>
                <div class="cal-item" @click="place(9)">9</div>
                <div class="cal-item" @click="place('-')">-</div>
                <div class="cal-item" @click="squarenum()">²</div>
            </div>
            <div class="cal-row-3">
                <div class="cal-item" @click="place(4)">4</div>
                <div class="cal-item" @click="place(5)">5</div>
                <div class="cal-item" @click="place(6)">6</div>
                <div class="cal-item" @click="place('*')">*</div>
                <div class="cal-item" @click="place('(')">(</div>
            </div>
            <div class="cal-row-4">
                <div class="cal-item" @click="place(1)">1</div>
                <div class="cal-item" @click="place(2)">2</div>
                <div class="cal-item" @click="place(3)">3</div>
                <div class="cal-item" @click="place('/')">/</div>
                <div class="cal-item" @click="place(')')">)</div>
            </div>
            <div class="cal-row-5">
                <div class="cal-item" @click="place('.')">.</div>
                <div class="cal-item" @click="place(0)">0</div>
                <div class="cal-item" @click="equal()">=</div>
                <div class="cal-item" @click="reciprocial()">1/x</div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Calculator',
    data() {
        return {
            formula: "",
            result: 0
        }
    },

    methods: {
        place(element) {
            console.log("place..");
            this.formula += element;
        },

        equal() {
            console.log("equal..");
            this.result = eval(this.formula);
        },

        cleanRes() {
            console.log("cleanRes..");
            this.result = 0;
        },

        clean() {
            console.log("clean..");
            this.formula = "";
            this.result = 0;
        },

        back() {
            console.log("back..");
            this.formula = this.formula.slice(0, -1);
        },

        squareroot() {
            console.log("squareroot..");
            console.log(eval(this.formula));
            eval(this.formula) < 0 ? this.formula = "Cant sqrt negative values" : this.result = Math.sqrt(eval(this.formula));
        },
        squarenum() {
            console.log("squarenum..");
            console.log(eval(this.formula));
            this.formula = eval(this.formula * this.formula);
        },


        reciprocial() {
            console.log("reciprocial..");
            this.formula === "" || this.formula.endsWith("+" || "-" || "*" || "/" || "%") ? {} : this.formula = "1/(" + this.formula + ")";
            this.equal();
        }

    }
}
</script>
