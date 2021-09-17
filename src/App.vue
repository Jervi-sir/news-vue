<template>
  <div id="app">
    <header>
        <div class="logo">
            <a href="">
              <router-link to="/"><img src="https://fakeimg.pl/200x100/"></router-link>
            </a>
        </div>
        <div class="menu">
            <div class="item active">
              <router-link to="/post">Post</router-link>
            </div>
            <div class="item">
                <router-link to="/about">Videos</router-link>
            </div>
        </div>
    </header>
    <router-view/>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Tajawal&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Tajawal&display=swap');
.arabic {
    font-family: 'Tajawal', sans-serif;
}

html {
    box-sizing: border-box;
}

*, *::after, *::before {
    box-sizing: inherit;
    padding:0;
    margin: 0;
}

body {
    background-color: #F8F2EB;
    padding: 0 10%;
    font-family: 'Tajawal', sans-serif;
}


header {
    display: flex;
    justify-content: space-between;
    align-items: center;

}

header .menu {
    display: flex;
    justify-content: space-between;
}

header .logo {
    width: 20%;
}

header .menu {
    width: 10%;
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
