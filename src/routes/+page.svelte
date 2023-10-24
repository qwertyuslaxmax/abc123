   

   <script>
     let count = 0
     let multiplier = 1
     function ranDom(max){
        return Math.random() * max | 0;
     }
     function increment(){
        count = count + multiplier
     }
     function decrement(){
        count = count - multiplier
     }
     function multiplierInc(){
        multiplier += 1
     }
     function multiplierDec(){
        multiplier -= 1
     }
     function random(){
        let n = ranDom(2);
        if(n == 0){
            count += 1
        } else {
            count -= 1
        }
     }
    </script>

<style>
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
    .b {
        border-color:black;
        background-color:violet;
        color: red;
        padding: 10px;
        margin: 5px;
    }
    .ab {
        border-color:darkorchid;
        background-color:salmon;
        color:gold;
        padding: 10px;
        margin: 0 auto;
    }
    .abcde {
        border-color: mediumblue;
        background-color: chartreuse;
        color:blue;
        padding: 10px;
        margin: 5px;
    }
    .zxc{
        margin: 30px;
        color:crimson
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

        <button class="abcde" on:click={multiplierInc}>
            <p> Multiplier + 1 </p>
            {#if count == 1}
                <p> </p>
            {:else}
                <p> </p>
            {/if}
        </button>

        <h2 class='zxc> or </h2>

        <button class="ab" on:click={multiplierDec}>
            <p> Multiplier - 1 </p>
            if(multiplier <= 0){
                multiplier = 1}
        </button>

    </div>
</div>