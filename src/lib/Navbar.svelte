<script>
export let theme;

function toggleTheme(){

    if(typeof window !== 'undefined' && typeof localStorage !== 'undefined'){
       localStorage.setItem('theme', theme? 'light' : 'dark') 
       theme = !theme;
    }

}


</script>

<div>
    <nav class="navbar" class:light={!theme} class:dark={theme}>
        <a class="link" class:light={!theme} class:dark={theme} href="/">Home</a>
        <a class="link" class:light={!theme} class:dark={theme} href="/pageOne">Page One</a>
        <a class="link" class:light={!theme} class:dark={theme} href="/pageTwo">Page Two</a>
        <a class="link" class:light={!theme} class:dark={theme} href="/pageThree">Page Three</a>
        <button class:light={!theme} class:dark={theme} on:click={toggleTheme}>{theme? "Light" : "Dark"}</button>
    </nav>
</div>


<style>

.navbar{
    transition: all .2s ease-in-out;
    padding-top:2em;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
}
.light{
    background-color: #FFF;
    color: #242424;
}
.dark{
    background-color: #242424;
    color:#FFF;
}
.link{
    text-decoration: none;
    background-color: rgba(255, 255, 255, 0.0);
}
a:hover{
    text-decoration: underline;
    cursor: pointer;
}
button{
    cursor: pointer;
}
button:hover{
    opacity: .7;
}
</style>