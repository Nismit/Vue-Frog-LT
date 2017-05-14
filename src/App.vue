<template>
  <div>
    <header class="l-header">
      <h1>Frog LT Maneger</h1>
    </header> 
    
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
html {
  box-sizing: border-box;
  -ms-overflow-style: scrollbar;
  -webkit-tap-highlight-color: rgba(0,0,0,0);
  font-size: 15px;
}

body {
  margin: 0;
  -webkit-font-smoothing: subpixel-antialiased;
  -moz-osx-font-smoothing: auto;
  font-kerning: normal;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

.l-header {
  font-size: .7rem;
  text-align: center;
  border-bottom: 1px solid #ddd;
}

.l-header h1 {
  margin: 0;
  padding: .5em 0;
}
</style>
