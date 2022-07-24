<template>
    <header>
        <nav class="container">

            <img class="logo-site" src="https://archives.bulbagarden.net/media/upload/4/4b/Pok%C3%A9dex_logo.png" alt="logo pokedex">
            <ul>
                <li>
                    <a href="">Pokedex Completa</a>
                </li>
                <li>
                    <a href="">Sobre</a>
                </li>
                <li>
                    <a href="">Ajudar</a>
                </li>
            </ul>

        </nav>
    </header>
</template>

<script>

export default {
    name: 'Header',
    components: {

    }
}
</script>

<style scoped>
    header{
        background-color: chartreuse;
        width: 100%;
        height: 70px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    nav{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    a{
        color: #000;
    }

    .logo-site{
        width: 110px;
        height: 40px;
    }

    ul{
        list-style: none;
        display: flex;
        justify-content: space-between;
    }

    ul li{
        margin: 20px;
    }

</style>

