<template>
 <div class="calculator-border">
        <div class="calculator-display">
          <div class="calculator-formula" v-cloak>{{ formula }}</div>
          <div class="calculator-result" v-cloak>{{ result }}</div>
        </div>
            
          <div class="calculator-items">
          <div class="calculator-row-1">
          <div class="calculator-item" @click="cleanAll()">C</div>
          <div class="calculator-item" @click="square()">√</div>
          <div class="calculator-item" @click="operate('%')">%</div>
          <div class="calculator-item" @click="operate('/')">/</div>
          </div>
                
           <div class="calculator-row-2">
          <div class="calculator-item" @click="operate(7)">7</div>
          <div class="calculator-item" @click="operate(8)">8</div>
          <div class="calculator-item" @click="operate(9)">9</div>
          <div class="calculator-item" @click="operate('*')">x</div>
          </div>

          <div class="calculator-row-3">
          <div class="calculator-item" @click="operate(4)">4</div>
          <div class="calculator-item" @click="operate(5)">5</div>
          <div class="calculator-item" @click="operate(6)">6</div>
          <div class="calculator-item" @click="operate('-')">-</div>
          </div>
                
          <div class="calculator-row-4">
          <div class="calculator-item" @click="operate(1)">1</div>
          <div class="calculator-item" @click="operate(2)">2</div>
          <div class="calculator-item" @click="operate(3)">3</div>
          <div class="calculator-item" @click="operate('+')">+</div>
          </div>
                
          <div class="calculator-row-5">
          <div class="calculator-item" @click="operate(100)">00</div>
          <div class="calculator-item" @click="operate(0)">0</div>
          <div class="calculator-item" @click="operate('.')">,</div>
          <div class="calculator-item" @click="equal()">=</div>
          </div>
        </div>
      </div>
</template>

<script>
export default {
  name: 'CalculatorContent',
  data () {
    return {
      formula :"",
      result : 0 
    }
  },

  methods:{
    operate(element){
      this.formula +=element
    },

    equal(){
      this.result = eval(this.formula)
    },

    cleanResult(){
      this.result = 0
    },

    cleanAll(){
      this.formula = ""
      this.result = 0
    },

    drop(){
      this.formula = this.formula.slice(0, -1)
    },

    square(){
      eval(this.formula)<0? this.formula = "Can not suqre the negative value" : this.result=Math.sqrt(eval(this.formula))
   },

   devided(){
    this.formula===""||this.formula.endsWith("+"||"-"||"*"||"/"||"%")? {} :  this.formula="1/("+this.formula+")";this.equal()
   },

   toggle(){
    this.formula===""||this.formula.endsWith("+"||"-"||"*"||"/"||"%")? {} :  this.formula.startsWith("-")?this.formula = Math.abs(eval(this.formula)).toString(): this.formula="-("+this.formula+")"
    this.equal()
   }
 }
}
</script>

<style>
.calculator-display{
  border-bottom: 2px solid #ffffff62;
  height: 100px;
  width: 100%;
  font-size: 2rem;
  margin: 0 auto;
  padding: 160px 0 18px 0;
  max-width: 390px;
  
}

.calculator-formula{
  height: 50px;
  width: 100%;
  text-align: right;
  box-sizing: border-box;
  padding-bottom: 26px;
  color: #fff;
  text-overflow: ellipsis;
  white-space:nowrap;
  overflow:hidden;
  font-size: 24px;
}

.calculator-result{
  font-weight: 800;
  width: 100%;
  text-align: right;
  box-sizing: border-box;
  color: #fff;
  font-size: 56px;
  text-overflow: ellipsis;
  white-space:nowrap;
  overflow:hidden;
}

.calculator-items{
  padding-top: 35px;
  margin: 0 auto;
  text-align: center;
  width: 100%;
  max-width: 460px;
}

.calculator-row-1,
.calculator-row-2,
.calculator-row-3,
.calculator-row-4,
.calculator-row-5{
  margin-bottom: 2.3%;
  width: 100%
}

 .calculator-item {
  text-align: center;
  width: 45px;
  height: 45px;
  padding: 10px 10px;
  margin: 10px 20px;
  border-radius: 50%;
  display: inline-block;
  text-align: center;
  color: #fff;
  cursor: pointer;
  transition: all 0.1s;
  font-size: 36px;
 

}
.calculator-item:hover{
  color: #f1f5f7;
  border-radius: 45%;
  background: rgba(255, 255, 255, 0.728);

}

.calculator-item:active{
  transform: translate(0.05rem,0.05rem);
}
</style>
