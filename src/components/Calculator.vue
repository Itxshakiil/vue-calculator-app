<template>
  <div>
    <div class="calculator">
      <div class="screen">
      <input type="text" align="right" v-model="result">
      <input type="text" align="right" v-model="num2">
      </div>
      <div class="buttons">
        <button class="key" @click="addnum(7)">7</button>
        <button class="key" @click="addnum(8)">8</button>
        <button class="key"  @click="addnum(9)">9</button>
        <button class="key operator" @click="addoperator('divide')">/</button>
        <button class="key" @click="addnum(4)">4</button>
        <button class="key" @click="addnum(5)">5</button>
        <button class="key" @click="addnum(6)">6</button>
        <button class="key operator" @click="addoperator('multiply')">&times;</button>
        <button class="key" @click="addnum(1)">1</button>
        <button class="key" @click="addnum(2)">2</button>
        <button class="key" @click="addnum(3)">3</button>
        <button class="key operator" @click="addoperator('sub')">-</button>
        <button class="key" @click="reset()">C</button>
        <button class="key" @click="addnum(0)">0</button>
        <button class="key" @click="calculate()">=</button>
        <button class="key operator" @click="addoperator('sum')">+</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
      return {
          result:0,
          num2:0,
          operator:"sum",
          lastkeyop:false,
      }
  },
  methods: {
      addnum:function(num){
          this.num2 = (this.num2 * 10) + num;
          this.lastkeyop=false;
      },
      addoperator:function(operator){ 
          if(! this.lastkeyop){
              this.calculate();
            this.lastkeyop=true;
          }
          this.operator = operator;
          // If everything is ok
         
      },
      calculate:function(){
          if(this.operator == "sum"){
              this.result= this.result + this.num2;
          }
          if(this.operator == "sub"){
              this.result= this.result - this.num2;
          }
          if(this.operator == "multiply"){
              this.result= this.result * this.num2;
          }
          if(this.operator == "divide"){
              if(this.num2 != 0 && this.num2 != null){
              this.result= this.result / this.num2;
              }else{
                  alert('Can not Divide to zero.');
              }
          }
          this.num2=null;
      },
      reset:function(){
          this.result=0;
          this.num2=0;
          this.operator="sum";
      }
  },
};
</script>

<style>
.calculator {
    max-width:300px;
    margin:auto;
    perspective: 1000;
    box-shadow: 1px 1px 19px #212121;
}
.screen{
    width:100%;
}
.buttons {
  display: grid;
  grid-template-rows: repeat(4, 1fr);
  grid-template-columns: repeat(4, 1fr);
}
.key{
    font-size:2rem;
    padding:1rem;
    width:75px;
    height:75px;
    background: #BDBDBD;
    border:none;
}
.key:focus{
    outline:none;
    box-shadow: 3px 3px 7px #212121;
}
.operator{
    background:#facf5a;
}
input{
    background: #233142;
    color:#fff;
    width:100%;
    padding:0.5rem 1rem;
    border:none;
    text-align: right;
    font-size: 1.3rem;
}
input:first-child{
    font-weight:bold;
}
</style>