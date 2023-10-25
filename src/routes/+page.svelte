<script lang="ts">
     let count = 0;
     let multiplier = 1;
     function ranDom(max: number){
        return Math.random() * max | 0;
     }
     function increment(){
        count = count + multiplier;
     }
     function decrement(){
        count = count - multiplier;
     }
     function random(){
        let n = ranDom(2);
        if(n == 0){
            count = count + multiplier;
        } else {
            count = count - multiplier;
        }
     }
</script>
<style>
    .parent-container {
    width: 500px;
    height: 500px;
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
    .parent-container form {
    margin:20px 0;
    padding: 20px;
    background-color: beige;
    border-radius: 50%;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  /* Style the input element inside the circular form */
  .parent-container form input[type="number"] {
    padding: 10px;
    border-radius: 50%;
    text-align: center; /* Center text horizontally */
    display: flex;
    flex-direction: column;
    align-items: center; /* Center text vertically */
    justify-content: center;
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

        <button class="b" on:click={increment}>
            <p> Increment </p>
            {#if count == 1}
                <p></p>
            {:else}
                <p></p>
            {/if}
        </button>

        <h2 class='zxc'> or </h2>

        <button class="abcde" on:click={decrement}>
            <p> Decrement </p>
            {#if count == 1}
                <p> </p>
            {:else}
                <p> </p>
            {/if}
        </button>

        <h2 class='zxc'> or </h2>

        <button class="ab" on:click={random}>
            <p> Random </p>
        </button>

        <h2 class='zxc'> or </h2>
        <div class='parent-container'>
            <form>
                <input type="number" placeholder="Multiplier" bind:value={multiplier}>
            </form>
        </div>

    </div>
</div>