<template>
  <v-row justify="center" align="center">
    <v-col class="test-pad">
      <div class="text-center">
        <p class="line-1 anim-typewriter">Hi. I'm Cory.</p>
      </div>
    </v-col>
        
     

  </v-row>
</template>

<script>


export default {
  components: {

  }
}
</script>

<style scoped>
.test-pad{
  padding-top: 8em;
}
html{
  min-height: 100%;
  overflow: hidden;
}
body{
  height: calc(100vh - 8em);
  padding: 4em;
  color: rgba(255,255,255,.75);
  font-family: monospace;  
  background-color: rgb(25,25,25);  
}
.line-1{
    position: relative;
    top: 50%;  
    width: 24em;
    margin: 0 auto;
    border-right: 2px solid rgba(255,255,255,.75);
    font-size: 180%;
    text-align: center;
    white-space: nowrap;
    overflow: hidden;
    transform: translateY(-50%);    
}

/* Animation */
.anim-typewriter{
  animation: typewriter 2s steps(60) 1s 1 normal both,
             blinkTextCursor 500ms steps(44) infinite normal;
}
@keyframes typewriter{
  from{width: 0;}
  to{width: 5.5em;}
}
@keyframes blinkTextCursor{
  from{border-right-color: rgba(255,255,255,.75);}
  to{border-right-color: transparent;}
}
</style>
