<script setup>
</script>

<template>
    <div class="navbar">
        <div class="menu-left">
            <button>Biografia</button>
            <button>Estilo</button>
        </div>

        <div class="titulo_site">
            <img src="../assets/silverspinningtoy.svg" alt="Pião" />
            <h1>Christopher <br> Nolan</h1>
        </div>
     
        <div class="menu-right">
            <button>Filmografia</button>
            <button>Início</button>
        </div>

        <div class="dropdown">
            <button class="dropdown-button">Menu</button>
            <div class="dropdown-content">
                <button>Biografia</button>
                <button>Estilo</button>
                <button>Filmografia</button>
                <button>Início</button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 43px; 
    background-color: #1C1C1C;
}

.titulo_site {
    display: flex;
    width: 16.3125rem; 
    height: 5.625rem;   
}
h1 {
    color: #D4E7F7;
    font-family: Arial, sans-serif;
    font-size: 1.25rem; 
    font-style: normal;
    font-weight: 400;
    line-height: 1.6; 
}

button {
    background-color: #1C1C1C;
    border: none;
    color: #D4E7F7;
    font-family: Arial, sans-serif;
    font-style: normal;
    cursor: pointer;
}
button:hover {
    border: 1px solid #D4E7F7; 
}

.dropdown {
    display: none;
    position: relative;
}
.dropdown-button {
    font-size: 1rem;
}
.dropdown-content {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #1C1C1C;
    padding: 10px;
    border-radius: 5px;
    z-index: 1;
}
.dropdown-content button {
    display: block;
    margin: 5px 0;
}
.dropdown-button:hover + .dropdown-content,
.dropdown-content:hover {
    display: block;
}

.menu-left,
.menu-right {
    display: flex;
    gap: 2.125rem;
}

@media (max-width: 768px) {
    .menu-left, .menu-right {
        display: none; 
    }
    .dropdown {
        display: block;
        margin-right: 25px; 
    }
    .navbar {
        padding: 20px;
        padding-left: 0px;
    }
    .titulo_site {
        height: 3.625rem;
    }
    h1 {
        font-size: 1rem;
        line-height: 1.2;
    }
}
</style>
