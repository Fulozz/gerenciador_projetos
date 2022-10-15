<template>
  <main>
    <section>
      <div class="child">
          <h2> Calculadora de idade  </h2> <br> <br>
          <b > Data de nascimento: <input type="date" id="DOB"> </b>
          <span id = "message"> </span> <br><br>  
          <button type="submit" @click = "ageCalculator()" >Calcular idade atual</button>
          <button type="submit" @click = "limpar()" > Limpar</button> <br><br>
          <h3 id="result" class="incorreto" align="center" ></h3> 
      </div>
    </section>
  </main>
</template>
<script>
export default {
  name: 'CalculadoraView',
  methods: {
    ageCalculator: ()=>{
      var userinput = document.getElementById("DOB").value;
      var dob = new Date(userinput);
      if(userinput==null || userinput=='') {
    
    document.getElementById("message").innerHTML = "**Coloque a data certa!"; 
    document.getElementById("result").innerHTML =  "Ainda não Nasceu";
    document.getElementById("result").style.color = "#FF0F0F";
    setTimeout(() => document.getElementById("message").innerHTML = "", 4500); 
    setTimeout(() => document.getElementById("result").innerHTML =  "", 4500); 
    
    return false; 

    } else {

    //Calculate the month of the User
      var date = new Date();
      var currentMonth = date.getMonth() - 1;  
      var nascMonth = dob.getMonth();  
      //calculate month difference from current date in time
      var month_diff = Date.now() - dob.getTime();
  
      //convert the calculated difference in date format
      var age_dt = new Date(month_diff);  
      //extract year from date    
      var year = age_dt.getUTCFullYear();
      //now calculate the age of the user
      var age = Math.abs(year - 1970)
      if (currentMonth >= nascMonth)  {
      //get months when current month is greater  
      var monthAge = currentMonth - nascMonth;  }
      else {  
      this.monthAge = 12 + currentMonth - nascMonth;  
    }
    //display the calculated age
      document.getElementById("result").style.color = "#32A80F";
      document.getElementById("message").innerHTML = ""; 
      return document.getElementById('result').innerHTML = "Idade é de: " + age + " anos e " + monthAge + " meses.";
    }
  },
  limpar: ()=>{
    document.getElementById('DOB').value = "";
    document.getElementById('result').innerHTML = "";
    document.getElementById("message").innerHTML = "";
    },
  },
};
</script>

<style scoped>
  *{
    text-align: center;
    align-items: center;
    z-index: 0;
}

h2{
    font-size: 2rem;
    color: #FFF;
}

section{
    display: flex;
    justify-content: center;
    align-items: center;
}
.child{

    margin-top: 15vh;
    margin-bottom: 15vh;
    background-color:  rgba(165, 42, 42, 0.8 );
    box-shadow: 5px 5px 3px;
    border-radius: 10px;
    padding: 70px;
  }

  body{
    background-color: #fff;
  }


  .incorreto{
    font: bold;
    color: #FFF;
  }

  #footer{
    height: 200px;
    width: 100%;
    background-color: #222;
    border-top: 4px solid #111;
    color: #FCBA03;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 78.2vh ;
    margin-bottom: 0;
}
.social-icon{
    color: #fff;
    margin-right: 10px;
    margin-left: 10px;
    transform: .5s;
}
.social-icon:hover{
    color: #FCBA03;
}
.social{
  display: flex;
  justify-content: center;
  text-align: center;
}
.foot{
    text-align: center;
    justify-content: center;
}
.contact{
    color:#FCBA03 !important;
}

#copyright{
  color: #fff;
  margin-top: 5px;
  font-family: Arial, Helvetica, sans-serif;
}
</style>