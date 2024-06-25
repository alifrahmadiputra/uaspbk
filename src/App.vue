<template>
  <div>
    <header class="header">
      <nav class="menu">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/todos">Todos</router-link></li>
          <li><router-link to="/posts">Posts</router-link></li>
          <li><router-link to="/albums">Albums</router-link></li>
          <li><router-link to="/about">About</router-link></li>
        </ul>
      </nav>
    </header>
    <router-view></router-view>
  </div>
</template>

<style>
.header {
  background-color: pink;
  padding: 10px;
}

.menu ul {
  display: flex;
  justify-content: left;
  list-style: none;
  font-size: 10px;
  padding: 0;
  margin: 0;
}

.menu ul li {
  margin: 0 15px;
}

.menu ul li a {
  text-decoration: none;
  color: white; 
  font-weight: bold;
  font-size: 20px; 
  padding: 10px 10px; 
  border-radius: 5px; 
}

.menu ul li a:hover {
  background-color: white; 
  transform: scale(1.05); 
  color: pink;
}
</style>
