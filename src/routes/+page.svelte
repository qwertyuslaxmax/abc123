    <script>
     let count = 0
     function increment(){
        count += 1
     }
     function decrement(){
        count -= 1
     }
    </script>

<div class='a'>
    <h1> </h1>
    <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
</div>
<div class='d'>

    <h2> {count} </h2>
</div>


<h3 class='d'>abc</h3>
<style>
    .d {
        color: firebrick;
    }
    .a {
        color: deepskyblue;
    }

    .b {
        padding: 10px;
        margin: 50px;

        padding-left: 50px;
    }
</style>
<button class="b" on:click={increment}>
    <p> increment </p>
    {#if count == 1}
        <p></p>
    {:else}
        <p></p>
    {/if}
</button>
<button class="b" on:click={decrement}>
    <p> decrement </p>
    {#if count == 1}
        <p> </p>
    {:else}
        <p> </p>
    {/if}
</button>