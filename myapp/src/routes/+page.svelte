<script>
  
  let textDisplay = "";
  let display = "";
  let isOperate = false;
  let operation = "";
  let subtotal = 0;
  let displaytotal = "0";
  let total;
  let res;
    
  const numbers = (e) =>{
    if(e.target.value != 0 || (e.target.value == 0 && textDisplay != "")){
      textDisplay += e.target.value + "";
      display += e.target.value;
    }
    
    isOperate = false;
    subtotal = eval(textDisplay);
    displaytotal = subtotal;
  };
  
  const operate = (e) =>{
    operation = e.target.value;
    
    if(isOperate == false){
      textDisplay += e.target.value + "";
      display += e.target.value;
    }else{
      res = textDisplay.slice(0, textDisplay.length-1);
      textDisplay = res + e.target.value + "";
      textDisplay = res + e.target.value;
    }
    
    isOperate = true;
  
  };
  
   const equals = () =>{
      textDisplay = "";
      total = subtotal;
      let eqtotal = total
      displaytotal = eqtotal;
    
   };
   
   const clear = () =>{
      textDisplay = "";
      total = 0;
      displaytotal = total;
      subtotal = 0;
   
   }
  
 
  
</script>

<h1>Basic Calculator</h1>

<table>
  <tr>
    <td><input type="text" bind:value = {textDisplay} disabled></td>
  </tr>
  <!--<tr>
    <td><input type="text" bind:value = {display} disabled="true"></td>
  </tr>-->
  <tr class="total">
    <td><input type="text" bind:value = {displaytotal} disabled></td>
  </tr>
  <tr>
    <td>
      <button on:click={clear}>CC</button>
      <button>()</button>
      <button>%</button>
      <button on:click={operate} value="/">&divide;</button>
    </td>
  <td>
      <button on:click={numbers} value=7>7</button>
      <button on:click={numbers} value=8>8</button>
      <button on:click={numbers} value=9>9</button>
      <button on:click={operate} value="*">&times;</button>
    </td>
    <td>
      <button on:click={numbers} value=4>4</button>
      <button on:click={numbers} value=5>5</button>
      <button on:click={numbers} value=6>6</button>
      <button on:click={operate} value="-">&minus;</button>
    </td>
    <td>
      <button on:click={numbers} value=1>1</button>
      <button on:click={numbers} value=2>2</button>
      <button on:click={numbers} value=3>3</button>
      <button on:click={operate} value="+">&plus;</button>
    </td>
    <td>
      <button on:click={numbers} value=0>0</button>
      <button on:click={numbers} value=".">.</button>
      <button class="equals" on:click={equals}>&equals;</button>
    </td>
  </tr>
</table>


