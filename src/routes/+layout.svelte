<script>
    import Navbar from "../lib/Navbar.svelte";

    let theme;
    if(typeof window !== 'undefined' && typeof localStorage !== 'undefined'){
       theme = localStorage.getItem('theme') === 'dark'? true :false ;
    }

</script>


<Navbar bind:theme={theme} />

<div class='app-container' class:light={!theme} class:dark={theme}>
    <slot></slot>
</div>


<style>
    .app-container{
        transition: all .2s ease-in-out;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width:100vw;
        height:100vh;
    }
    .light{
        background-color: #FFF;
        color: #242424;
    }
    .dark{
        background-color: #242424;
        color:#FFF;
    }
</style>