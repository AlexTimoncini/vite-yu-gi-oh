<script>
    export default{
        name: 'LoaderApp'
    }
</script>

<template>
    <div class="ivy_wrapper">
        <div class="container">
          <div class="baton-0"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-1"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-2"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-3"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-4"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-5"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-6"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-7"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-8"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-9"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-10"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-11"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-12"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-13"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-14"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-15"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-16"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-17"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-18"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-19"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-20"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-21"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-22"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-23"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-24"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-25"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-26"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-27"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-28"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-29"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-30"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-31"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-32"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-33"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-34"><div class="metronome"><div class="baton"></div></div></div>
          <div class="baton-35"><div class="metronome"><div class="baton"></div></div></div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    .container {
  display:block;
  height:300px;
  width:300px;
  margin:0 auto;
}
.baton {
  display:block;
  height:2px;
  width:70px;
  background-color:#459fa5;
  animation: scale 1.25s infinite linear;
  -webkit-transform-origin: 0;
  -moz-transform-origin: 0;
  -ms-transform-origin: 0;
  -o-transform-origin: 0;
  transform-origin: 0;
  -webkit-transform: rotate(-10deg);
  -moz-transform: rotate(-10deg);
  -ms-transform: rotate(-10deg);
  -o-transform: rotate(-10deg);
  transform: rotate(-10deg);
  &:before {
    content:'';
    display:block;
    height:5px;
    width:5px;
    background-color:#f5a51c;
    position:absolute;
    top:-2px;
    -webkit-border-radius: 5px;
    -moz-border-radius: 5px;
    -ms-border-radius: 5px;
    -o-border-radius: 5px;
    border-radius: 5px;
  }
  &:after {
    content:'';
    display:block;
    height:5px;
    width:5px;
    background-color:#f5a51c;
    position:absolute;
    top:-2px;
    right:0;
    -webkit-border-radius: 5px;
    -moz-border-radius: 5px;
    -ms-border-radius: 5px;
    -o-border-radius: 5px;
    border-radius: 5px;
  }
}

.metronome {
  -webkit-transform-origin: 0;
  -moz-transform-origin: 0;
  -ms-transform-origin: 0;
  -o-transform-origin: 0;
  transform-origin: 0;
  animation: metronome 1.25s infinite linear;
}

@for $i from 0 through 35 {
  .baton-#{$i} {
    height:1px;
    width:150px;
    position:absolute;
    top:calc(50% - 8px);
    -webkit-transform-origin: 100%;
    -moz-transform-origin: 100%;
    -ms-transform-origin: 100%;
    -o-transform-origin: 100%;
    transform-origin: 100%;
    -webkit-transform: rotate($i * 10deg);
    -moz-transform: rotate($i * 10deg);
    -ms-transform: rotate($i * 10deg);
    -o-transform: rotate($i * 10deg);
    .baton, .baton:after, .metronome {
      animation-delay: -$i * 0.14s;
    }
  }
}

@keyframes metronome {
  0% {
    -webkit-transform: rotate(-25deg);
    -moz-transform: rotate(-25deg);
    -ms-transform: rotate(-25deg);
    -o-transform: rotate(-25deg);
    transform: rotate(-25deg); }
  50% {
    -webkit-transform: rotate(25deg);
    -moz-transform: rotate(25deg);
    -ms-transform: rotate(25deg);
    -o-transform: rotate(25deg);
    transform: rotate(25deg); }
  100% {
    -webkit-transform: rotate(-25deg);
    -moz-transform: rotate(-25deg);
    -ms-transform: rotate(-25deg);
    -o-transform: rotate(-25deg);
    transform: rotate(-25deg); }
}

@keyframes scale {
  0% {
    -webkit-transform: scaleX(1);
    -moz-transform: scaleX(1);
    -ms-transform: scaleX(1);
    -o-transform: scaleX(1);
    transform: scaleX(1); }
  25% {
    -webkit-transform: scaleX(0.74);
    -moz-transform: scaleX(0.74);
    -ms-transform: scaleX(0.74);
    -o-transform: scaleX(0.74);
    transform: scaleX(0.74); }
  50% {
    -webkit-transform: scaleX(1);
    -moz-transform: scaleX(1);
    -ms-transform: scaleX(1);
    -o-transform: scaleX(1);
    transform: scaleX(1); }
  75% {
    -webkit-transform: scaleX(1.16);
    -moz-transform: scaleX(1.16);
    -ms-transform: scaleX(1.16);
    -o-transform: scaleX(1.16);
    transform: scaleX(1.16); }
  100% {
    -webkit-transform: scaleX(1);
    -moz-transform: scaleX(1);
    -ms-transform: scaleX(1);
    -o-transform: scaleX(1);
    transform: scaleX(1); }
  }
</style>
