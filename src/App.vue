<template>
<div>
<header>
  <router-link to="/">
    <h1><span>Vue</span>Movies</h1>
  </router-link>
</header>
<main>
    <router-view/>
</main>
</div>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', sans-serif;
  &::selection {
    background: transparentize(#42B883, 0.5);
  }
}
body {
  background: linear-gradient(rgb(49, 49, 49), rgb(66, 62, 62), rgb(34, 34, 34));
}
a {
  text-decoration: none;
}
header {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 16px;
  background: linear-gradient(rgb(34, 34, 34), rgb(92, 92, 92));
  box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.1);
  h1 {
    color: #FFF;
    font-size: 28px;
    span {
      color: #42B883;
    }
  }
}
</style>
