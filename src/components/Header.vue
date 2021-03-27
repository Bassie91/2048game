<template>
<div class="container">
    <div class="logo">
        <h3>The game</h3>
        <h1>2048</h1>
    </div>
    <div class="menu">
        <ul>
            <li><router-link to="/about">About</router-link> </li>
            <li><router-link to="/">New Game</router-link></li>
            <li><a href="#">Creator</a></li>
        </ul>
    </div>
</div>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped>
.container {
    display: flex;
    background-color: #2c3e50;
    justify-content: space-between;
    align-items: center;
    padding: 1.1rem 1.3rem;
}

.logo {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #ecf0f1;
}

.menu ul {
    list-style: none;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}

.menu ul li {
    margin-left: 20px;
}

.menu ul li a{
    text-decoration: none;
    color: #ecf0f1;
}

.menu ul li a:hover {
    color: #76c8ff;
}
</style>