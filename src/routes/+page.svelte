
<script lang="ts">

    import { onMount } from 'svelte';

let count = 0;
let  multiplier = null;
let currentText = "game1";

function slide() {
  document.getElementById("game1")!.style.display = "none";
  document.getElementById("game2")!.style.display = "none";

  if (currentText === "game1") {
    currentText = "game2";
  } else {
    currentText = "game1";
  }

  document.getElementById(currentText)!.style.display = "block";
}

onMount(() => {
  // Code to run when the component is mounted
  slide(); // Initial slide
  setInterval(slide, 5000); // Repeat every 5 seconds
});

  function ranDom(max: number) {
    return Math.random() * max | 0;
  }

  function increment() {
    count = count + multiplier;
  }

  function decrement() {
    count = count - multiplier;
  }

  function reset1() {
    count = 0;
    multiplier = null;
  }

  function random() {
    let n = ranDom(2);
    if (n == 0) {
      count = count + multiplier;
    } else {
      count = count - multiplier;
    }
  }
</script>
<style>
    .parent-container {
        display: flex; /* Use flexbox layout */
        justify-content: center; /* Center content horizontally */
        align-items: center; /* Center content vertically */
        width: 100%; /* Make the container take up the full width of its parent */
}

   .ert{
       text-align: center;
       font-size: 1.5rem;
       background-color: beige;
   }
   .d {
       color: firebrick;
       margin: 0 auto;
   }
   .a {
       color: rgb(0, 191, 255);
       margin: 0 auto;
       
   }
   .buttons{
       font-size: 1.1rem;
       font-family: Georgia, 'Times New Roman', Times, serif
   }
   .abcde{
   border-color: black;
   background-color: violet;
   color: red;
   padding: 10px;
   margin: 5px;
   transition: background-color 0.2s;
   }
   .abcde:active,
   .ab:active {
   background-color: darkviolet; /* Change the background color when the button is clicked */
   }
   .fg:active,
   .b:active {
   background-color: tomato; /* Change the background color when the button is clicked */
   }
   .b{
   border-color:chocolate;
   background-color: chartreuse;
   color: green;
   padding: 10px;
   margin: 5px;
   transition: background-color 0.2s;
   }
   .ab{
   border-color:navy;
   background-color: lavender;
   color: orange;
   padding: 10px;
   margin: 5px;
   transition: background-color 0.2s;
   }
   .zxc{
       margin: 30px;
       color:crimson
   }
   .button-container{
        display: flex;
        align-items: center;
        justify-content: center;
   }
   .fg{
    border-color:indigo;
    background-color:lightslategray; 
    color: gold;
    padding: 10px;
    margin: 5px;
    transition: background-color 0.2s;
   }
   form {
   margin: 10px 0;
   padding: 10px;
   background-color: beige;
   border: none;
   border-radius: 15px; /* Increase the border-radius for more rounded corners */
   }
   body {
    border: 20px solid #333; /* Border width and color */
    border-radius: 10px; /* Border corner radius for rounded corners */
    padding: 10px; /* Padding inside the border */
    
    height: 100vh; /* Set the body's height to 100% of the viewport height */
    box-sizing: border-box; /* Include padding and border in the element's total width and height */
    }

   form input[type="number"] {
       padding: 10px;
       border: 1px solid #999;
       border-radius: 10px; /* Increase the border-radius for more rounded corners */
       text-align: center;
 }

</style>

<div class='ert'>
   <div class='a'>
       <h1> Advanced counter </h1>
   </div>
   <div class='d'>
       <h2> {count} </h2>
       <h2> {multiplier} </h2>
   </div>

   <h3 class='d'>Actions:</h3>

   <div class='buttons'>

    <div class="button-container">
        <button class="b" on:click={increment}>
          <p> Increment </p>
        </button>
        <h2 class="zxc"> or </h2>
        <button class="abcde" on:click={decrement}>
          <p> Decrement </p>
        </button>
        <h2 class='zxc'> or </h2> <!-- Move the "or" text here -->

       <button class="ab" on:click={random}>
           <p> Random </p>
       </button>
       <h2 class='zxc'> or </h2>
       <button class="fg" on:click={reset1}>
           <p> Reset to Zero </p>
       </button>

       
        
    </div>
    <h3 class='zxc'>Multiplier:</h3>
    <div class='parent-container'>
        <form>
            <input type="number" placeholder="Multiplier" bind:value={multiplier}>
        </form>
    </div>
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img src="./Duolingo Ayisi.png" alt="Image of Duolingo Ayisi">
    <h1 id="game2">Play Tank Aiming 2 by tadim15 on Scratch</h1>
   </div>
</div>