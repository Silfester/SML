<template>
  <div class="Logo fixed-top-left">
    <b-img src="../static/logo.png" fluid alt="Responsive image"></b-img>
  </div>
</template>
<style>
.Logo {
  position: fixed;
  top: 10px;
  left: 10px;
  width: 100px;
  height: auto;
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
