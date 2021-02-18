<template>
<div style="background-color:black;">
      <div class="sidenav">
        <img src="../assets/healthify_icon.jpg" class="image">

         <span style="font-size:20px; color:dodgerblue; border-style:solid; border-width: 4px; border-color:dodgerblue; border-radius:15px; "><b>Contact us :-</b></span>
        <button class="btn3" style="margin-top:20px;">WHATSAPP</button>
        <button class="btn3">E-MAIL</button>
      <a href="https://www.facebook.com/paraskumar.patel.77/" target="_blank">  <button class="btn3">FACEBOOK</button> </a>
       <button class="btn3">INSTAGRAM</button> 
        <button class="btn3">TWEETER</button>
       <button class="btn3" style="margin-bottom:80px">LINKED IN</button>

        
  </div>
  
  <div class="column middle">
    <div class="container">
      <button class="btn2" v-on:click="decrementimg()">&#8249;</button>
      <img src="../assets/Cycling.jpg" style="width:100%"/>
      <button class="btn" v-on:click="incrementimg()">&#8250;</button>
    </div><br><br>
    <h1>Welcome Cadet</h1><br><br>
    <div8>
    <h6 class="calc"><br><br><br><br>
        <span>Calculate your BMR :-</span> <br><br>
         <div>
    <b-form-group label="Select your gender :-" v-slot="{ ariaDescribedby }" style="background-color: cornsilk">
      <b-form-radio v-model="selected" :aria-describedby="ariaDescribedby" name="some-radios" value="Male" style="background-color: cornsilk">Male</b-form-radio>
      <b-form-radio v-model="selected" :aria-describedby="ariaDescribedby" name="some-radios" value="Female" style="background-color: cornsilk">Female</b-form-radio>
    </b-form-group>
  </div>
         <p1>Enter your Weight:- <input type="number" placeholder="In Kilos" v-model="weight"> Kg</p1><br><br>
         <p1>Enter your Height:- <input type="number" placeholder="In Inches" v-model="height">Inch</p1><br><br>
         <p1>Enter your Age:-    <input type="number" placeholder="In Years" class="input" v-model="age">Years</p1><br><br>
        <div1> <button class="btn4" v-on:click="bmrcalc(selected)">Calculate BMR</button><button class="btn4" v-on:click="Clear1()">Clear All</button></div1><br><br>
         <p1  class="result">Your BMR</p1> :- <output>  {{bmr}}  </output><br><br>
         <hr>
         <span>Calculate your Calories burnt today :-</span> <br><br>

         <p4 style="font-size:20px,"> *Enter active time spent(or leave zero)</p4><br><br>
    
        <p1><b>Walking time:-              </b><input style="text-align:right; margin-left:180px" type="number" placeholder="In Minutes" v-model="walk"> minutes </p1><br><br>
        <p1><b>Yoga time:-                 </b><input style="text-align:right; margin-left:220px" type="number" placeholder="In Minutes" v-model="yoga"> minutes </p1><br><br>
        <p1><b>Jogging time:-              </b><input style="text-align:right; margin-left:180px" type="number" placeholder="In Minutes" v-model="jogg"> minutes </p1><br><br>
        <p1><b>Cycling time:-              </b><input style="text-align:right; margin-left:180px" type="number" placeholder="In Minutes" v-model="cycle"> minutes </p1><br><br>
        <p1><b>Weight Training:-           </b><input style="text-align:right; margin-left:140px" type="number" placeholder="In Minutes" v-model="train"> minutes </p1><br><br>
        <p1><b>Moderate Intensity Cardio:- </b><input style="text-align:right" type="number" placeholder="In Minutes" v-model="cardio1"> minutes </p1><br><br>
        <p1><b>High Intensity Cardio:-     </b><input style="text-align:right; margin-left:70px" type="number" placeholder="In Minutes" v-model="cardio2"> minutes </p1><br><br>
  
        <div1> <button class="btn4" v-on:click="tcbcalc()">Calculate Calories</button><button class="btn4" v-on:click="Clear2()">Clear All</button></div1><br><br>
         <p1  class="result">Total Calories Burnt</p1> :- <output>  {{tcb}}  </output><br><br>
         <hr>

 <span>Calculate your Calories Gain today :-</span> <br><br>

         <p4 style="font-size:20px,"> *Enter amount according to postfix quantity</p4><br><br>
    
        <p1><b>Rice :-   <b-dropdown id="dropdown-1" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval1('Plain')">Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval1('Jeera Fried')">Jeera Fried</b-dropdown-item>
    <b-dropdown-item v-on:click="putval1('Pulao')">Pulao</b-dropdown-item>
    <b-dropdown-item v-on:click="putval1('Khichdi')">Khichdi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval1('Biryani')">Biryani</b-dropdown-item>
  </b-dropdown> {{dropb1}}  </b><input style="text-align:right; width:70px;" type="number" v-model="rice">  plate(1p=125gm) </p1><br><br>
        
        <p1><b>Daal :-  <b-dropdown id="dropdown-2" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval2('Plain')">Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval2('Fried')">Fried</b-dropdown-item>
  </b-dropdown> {{dropb2}}               </b><input style="text-align:right; width:70px;" type="number" v-model="daal"> katori(1k=100ml) </p1><br><br>
        
        <p1><b>Roti :-    <b-dropdown id="dropdown-3" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval3('Plain')">Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval3('Tandoori')">Tandoori Roti</b-dropdown-item>
    <b-dropdown-item v-on:click="putval3('Plain Paratha')">Plain Paratha</b-dropdown-item>
    <b-dropdown-item v-on:click="putval3('Puri')">Puri</b-dropdown-item>
    <b-dropdown-item v-on:click="putval3('Bhature')">Bhature</b-dropdown-item>
    <b-dropdown-item v-on:click="putval3('Aloo Paratha')">Aloo Paratha</b-dropdown-item>
  </b-dropdown> {{dropb3}}             </b><input style="text-align:right; width:70px;" type="number" v-model="roti"> piece </p1><br><br>
        
        <p1><b>Sabzi 1 :-    <b-dropdown id="dropdown-4" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval4('Veg Sabzi')">Veg Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval4('Masala Sabzi')">Masala Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval4('Chicken Curry')">Chicken Curry</b-dropdown-item>
    <b-dropdown-item v-on:click="putval4('Fried Sabzi')">Fried Sabzi</b-dropdown-item>
  </b-dropdown> {{dropb4}}                  </b><input style="text-align:right; width:70px;" type="number" v-model="sabzi1"> katori </p1><br><br>
        
        <p1><b>Sabzi 2 :-    <b-dropdown id="dropdown-5" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval5('Veg Sabzi')">Veg Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval5('Masala Sabzi')">Masala Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval5('Chicken Curry')">Chicken Curry</b-dropdown-item>
    <b-dropdown-item v-on:click="putval5('Fried Sabzi')">Fried Sabzi</b-dropdown-item>
  </b-dropdown> {{dropb5}}              </b><input style="text-align:right; width:70px;" type="number" v-model="sabzi2"> katori </p1><br><br>
        
        <p1><b>Sabzi 3 :-    <b-dropdown id="dropdown-6" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval6('Veg Sabzi')">Veg Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval6('Masala Sabzi')">Masala Sabzi</b-dropdown-item>
    <b-dropdown-item v-on:click="putval6('Chicken Curry')">Chicken Curry</b-dropdown-item>
    <b-dropdown-item v-on:click="putval6('Fried Sabzi')">Fried Sabzi</b-dropdown-item>
  </b-dropdown> {{dropb6}}           </b><input style="text-align:right; width:70px;" type="number" v-model="sabzi3"> katori </p1><br><br>
       
        <p1><b>Snack 1 :-  <b-dropdown id="dropdown-7" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval7('Baked or Plain')">Baked or Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval7('Light Fried')">Light Fried</b-dropdown-item>
    <b-dropdown-item v-on:click="putval7('Deep Fried')">Deep Fried</b-dropdown-item>
  </b-dropdown> {{dropb7}}     </b><input style="text-align:right; width:70px;" type="number" v-model="snack1"> plate </p1><br><br>
        
        <p1><b>Snack 2 :-<b-dropdown id="dropdown-8" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval8('Baked or Plain')">Baked or Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval8('Light Fried')">Light Fried</b-dropdown-item>
    <b-dropdown-item v-on:click="putval8('Deep Fried')">Deep Fried</b-dropdown-item>
  </b-dropdown> {{dropb8}}     </b><input style="text-align:right; width:70px;" type="number" v-model="snack2"> plate </p1><br><br>
        
        <p1><b>Snack 3 :-  <b-dropdown id="dropdown-9" text="Select" class="m-md-2">
    <b-dropdown-item v-on:click="putval9('Baked or Plain')">Baked or Plain</b-dropdown-item>
    <b-dropdown-item v-on:click="putval9('Light Fried')">Light Fried</b-dropdown-item>
    <b-dropdown-item v-on:click="putval9('Deep Fried')">Deep Fried</b-dropdown-item>
  </b-dropdown> {{dropb9}}   </b><input style="text-align:right; width:70px;" type="number" v-model="snack3"> plate </p1><br><br>

        <div1> <button class="btn4" v-on:click="tcgcalc()">Calculate Calories</button><button class="btn4" v-on:click="Clear3()">Clear All</button></div1><br><br>
         <p1  class="result">Total Calories Gained</p1> :- <output>  {{tcg}}  </output><br><br><br><br>
    </h6><br><br>
    </div8>
    <div style="
  color: whitesmoke !important;
  background-color:black  !important;">
    <span>ABOUT US</span><hr>
    <p>Your health is now our first priority,</p> 
    <p>We here at Healthify.com will guide you to an healthy lifestyle.</p><hr>
    <p>  From measuring your daily calories burnt to counting your calories gained, we will let you assure about your daily, weekly,monthly as well as yearly statistics of weight gains and losses.</p><hr>
     <p> We will provide you the right training materials(Videos, Blogs, Articles, etc.) according to your health reports.</p><hr>
     <p> We will also guide and train you to experience the real potentials of your body. We have Yoga as well as Martial arts materials which are guided by real professionals.
    </p><hr>
    <br><br>
    <p><span>DEVELOPER NAME</span> :- PARAS KUMAR PATEL</p>
    <p><span>EMAIL ID</span> :- pp971827@gmail.com</p>
     <p><span>MOBILE NUMBER</span> :- 9039933558</p>
    </div>
  </div>
</div>
</template>
<script>
export default {
    name: 'main1',  
    data(){
        return{
        weight:0,
        height:0,
        age:0,
        bmr:0,
        selected: '',
        walk:0,
        yoga:0,
        jogg:0,
        cycle:0,
        train:0,
        cardio1:0,
        cardio2:0,
        tcb:0,
        dropb1:'Select',
        dropb2:'Select',
        dropb3:'Select',
        dropb4:'Select',
        dropb5:'Select',
        dropb6:'Select',
        dropb7:'Select',
        dropb8:'Select',
        dropb9:'Select',
        rice:0,
        daal:0,
        roti:0,
        sabzi1:0,
        sabzi2:0,
        sabzi3:0,
        snack1:0,
        snack2:0,
        snack3:0,
        tcg:0,
        i:0,
        source:[
          "../assets/Cycling.jpg",
          "../assets/Running.jpg",
          "../assets/Strong.jpg",
          "../assets/Body.jpg"
        ]
  
        }
    },
    methods: {
        bmrcalc(selected){
              if(selected=="Male"){
                 this.bmr=66+(2.2*6.2*this.weight)+(12.7*this.height)-(6.79*this.age);
            }
              else if(selected=="Female"){
                  this.bmr=655.1+(2.2*4.35*this.weight)+(4.7*this.height)-(4.7*this.age);
            }
            else{ 
                this.bmr=0;
            }
        },
        tcbcalc(){
          this.tcb= (1.2*this.bmr)+(this.weight*((2.7*this.walk)+(3*this.yoga)+(6*this.jogg)+(4*this.cycle)+(4*this.train)+(7*this.cardio1)+(9*this.cardio2))/60);
        },
        Clear1(){
            this.height=0;
            this.weight=0;
            this.age=0;
            this.bmr=0;
        },
        Clear2(){
            this.walk=0;
            this.yoga=0;
            this.jogg=0;
            this.cycle=0;
            this.train=0;
            this.cardio1=0;
            this.cardio2=0;
            this.tcb=0;
        },
        Clear3(){
            this.rice=0;
            this.daal=0;
            this.roti=0;
            this.sabzi1=0;
            this.sabzi2=0;
            this.sabzi3=0;
            this.snack1=0;
            this.sanck2=0;
            this.snack3=0;
            this.tcg=0;
        },
        putval1(data){
          this.dropb1=data;
        },
        putval2(data){
          this.dropb2=data;
        },
        putval3(data){
          this.dropb3=data;
        },
        putval4(data){
          this.dropb4=data;
        },
        putval5(data){
          this.dropb5=data;
        },
        putval6(data){
          this.dropb6=data;
        },
         putval7(data){
          this.dropb7=data;
        },
         putval8(data){
          this.dropb8=data;
        },
         putval9(data){
          this.dropb9=data;
        },
        tcgcalc(){

           if(this.dropb1=="Plain"){
            this.rice=this.rice*300;
          }
          else if(this.dropb1=="Jeera Fried"){
            this.rice=this.rice*450;
          }
          else if(this.dropb1=="Pulao"){
            this.rice=this.rice*550;
          }
          else if(this.dropb1=="Khichdi"){
            this.rice=this.rice*350;
          }
           else if(this.dropb1=="Biryani"){
            this.rice=this.rice*700;
          }
           

          if(this.dropb2=="Plain"){
            this.daal=this.daal*100;
          }
          else if(this.dropb2=="Fried"){
            this.daal=this.daal*150;
          }
          
          if(this.dropb3=="Plain"){
            this.roti=this.roti*100;
          }
          else if(this.dropb3=="Tandoori"){
            this.roti=this.roti*70;
          }
          else if(this.dropb3=="Plain Paratha"){
            this.roti=this.roti*125;
          }
          else if(this.dropb3=="Puri"){
            this.roti=this.roti*100;
          }
           else if(this.dropb3=="Bhature"){
            this.roti=this.roti*200;
          }
          else if(this.dropb3=="Aloo Paratha"){
            this.roti=this.roti*180;
          }

          if(this.dropb4=="Veg Sabzi"){
            this.sabzi1=this.sabzi1*200;
          }
          else if(this.dropb4=="Masala Sabzi"){
            this.sabzi1=this.sabzi1*250;
          }
          else if(this.dropb4=="Chicken Curry"){
            this.sabzi1=this.sabzi1*450;
          }
          else if(this.dropb4=="Fried Sabzi"){
            this.sabzi1=this.sabzi1*300;
          }
           
           if(this.dropb5=="Veg Sabzi"){
            this.sabzi2=this.sabzi2*200;
          }
          else if(this.dropb5=="Masala Sabzi"){
            this.sabzi2=this.sabzi2*250;
          }
          else if(this.dropb5=="Chicken Curry"){
            this.sabzi2=this.sabzi2*450;
          }
          else if(this.dropb5=="Fried Sabzi"){
            this.sabzi2=this.sabzi2*300;
          }
          
           if(this.dropb6=="Veg Sabzi"){
            this.sabzi3=this.sabzi3*200;
          }
          else if(this.dropb6=="Masala Sabzi"){
            this.sabzi3=this.sabzi3*250;
          }
          else if(this.dropb6=="Chicken Curry"){
            this.sabzi3=this.sabzi3*450;
          }
          else if(this.dropb6=="Fried Sabzi"){
            this.sabzi3=this.sabzi3*300;
          }
           
          if(this.dropb7=="Baked or Plain"){
            this.snack1=this.snack1*250;
          }
          else if(this.dropb7=="Light Fried"){
            this.snack1=this.snack1*500;
          }
          else if(this.dropb7=="Deep Fried"){
            this.snack1=this.snack1*800;
          }

          if(this.dropb8=="Baked or Plain"){
            this.snack2=this.snack2*250;
          }
          else if(this.dropb8=="Light Fried"){
            this.snack2=this.snack2*500;
          }
          else if(this.dropb8=="Deep Fried"){
            this.snack2=this.snack2*800;
          }

          if(this.dropb9=="Baked or Plain"){
            this.snack3=this.snack3*250;
          }
          else if(this.drop9=="Light Fried"){
            this.snack3=this.snack3*500;
          }
          else if(this.dropb9=="Deep Fried"){
            this.snack3=this.snack3*800;
          }

          this.tcg= this.rice+this.daal+this.roti+this.sabzi1+this.sabzi2+this.sabzi3+this.snack1+this.snack2+this.snack3 ;
        },
        incrementimg(){
          if((this.i>=0) && (this.i<3)){
            this.i++;
          }
        },
        decrementimg(){
          if((this.i<=3) && (this.i>0)){
            this.i--;
          }
        }
    }
}
</script>
<style scoped>
div{
    background-color: cornflowerblue;
}
.column {
  float: left;
  padding: 10px;
}

/* Left and right column */


.sidenav {
  height: auto; /* Full-height: remove this if you want "auto" height */
  width: 225px; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */ /* Stay on top */
   /* Stay at the top */
  left: 0;/* Black *//* Disable horizontal scroll */
  bottom: -360px;
  padding-top: 20px;
  padding-bottom: 50px;
  background-color:black;
  margin-bottom:300px;
}
/* Middle column */
.column.middle {
  background-color: black;
  margin-left: 225px;
  margin-bottom:40px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive layout - makes the three columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .column.side, .column.middle {
    width: 100%;
  }
}
h1,h2{
    font-family:'Courier New', Courier, monospace;
    font-size: 80px;
    color: darkmagenta;
    font-weight: bold;
    border-style: none none solid none;
    border-color:darkmagenta;
    border-width:5px;
}
p{
  font-family:'Times New Roman', Times, serif;
    font-size: 30px;
    color: black;
}
/* Container needed to position the button. Adjust the width as needed */
.container {
  position: relative;
  width: 100%;
  color: rgb(215, 217, 240);
  background-color: rgb(215, 217, 240);
}

/* Make the image responsive */
.container img {
  width: 100%;
  height: auto;
}

/* Style the button and place it in the middle of the container/image */
.container .btn {
  position: absolute;
  top: 50%;
  right: 0%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  background-color:black;
  color:white;
  font-size: 16px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 50%;
}

.container .btn:hover {
  background-color: black;
}
.container .btn2 {
  position: absolute;
  top: 50%;
  left: 4%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  background-color:black;
  color: white;
  font-size: 16px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 50%;
}
.container .btn2:hover {
  background-color: black;
}
.btn2 {
  background-color:black;
  color: white;
  font-size: 16px;
  padding: 12px 24px;
  border: none;
  cursor: pointer;
  border-radius: 5%;
}
.list {
  list-style-type:none;
}

.btn3 {
  border: 2px solid black;
  background-color: white;
  color: black;
  font-size: 25px;
  font-weight: bold;
  cursor: pointer;
  border-color: #2196F3;
  color: dodgerblue;
  width: 200px;
  border-radius: 15px;
  margin-bottom:20px;
}
.btn3:hover {
   background: #2196F3;
  color: white;
}

.calc{
    text-align: center;
    background-color: cornsilk;
    font-size: 30px;
    color: black;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
span{
    text-decoration:underline; 
    font-size:50px;
    color:dodgerblue;
}
.input{
    margin-left: 42px;
}
.result{
    text-decoration: underline;
    font-size:40px;
    color: green;
}
output{
    font-size: 40px;
}
.btn4 {
  border: 2px solid black;
  background-color: white;
  color: black;
  padding: 14px 28px;
  font-size: 25px;
  font-weight: bold;
  cursor: pointer;
  border-color: #2196F3;
  color: dodgerblue;
  width: 400px;
  margin-right: 25px ;
}
.btn4:hover {
   background: #2196F3;
  color: white;
}
div1{
    background-color: cornsilk;
    align-content: center;
}
hr{
  margin-top: 0.5em;
  margin-bottom: 0.5em;
  margin-left: 0px;
  margin-right: auto;
  border-style:solid;
  border-width: 4px;
  border-color:red;
}
p{
  background-color: black !important;
  color:whitesmoke  !important;
}
.image{
    z-index:-2 !important;
    margin-top:80px;
    margin-bottom:40px;
    margin-left:32px;
    margin-right:32px;
    width:151px;
    height:140px;
}
</style>