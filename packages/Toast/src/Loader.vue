<template lang="html">
 <div class="wd-spin-wrap" :class="type">
   <div v-for="i in 12"></div>
 </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'big'
    }
  },
  mounted(){
  }
}
</script>

<style lang="sass">
.wd-spin-wrap {
  position: relative;
}
.wd-spin-wrap.big{
  width: 60px;
  height: 60px;
  left: 50%;
  margin-bottom: 24px;
}
.wd-spin-wrap.small{
  width: 48px;
  height: 48px;
  display: inline-block;
  vertical-align: middle;
  margin-right: -5px;/*no*/
}
@for $i from 1 through 12 {
  .wd-spin-wrap > div:nth-child(#{$i}) {
    transform: rotate((30deg *($i - 1)));
    animation: wd-spin-wrap 1.2s (0.1*$i) * 1s infinite ease-in-out;
  }
}
.wd-spin-wrap.small > div {
  background-color: #000;
  width: 2px;/*no*/
  height: 5px;/*no*/
  border-radius: 100%;/*no*/
  -webkit-animation-fill-mode: both;
          animation-fill-mode: both;
  position: absolute;
  transform-origin: center 10px; /*no*/
}
.wd-spin-wrap.big > div {
  background-color: #fff;
  width: 3px;/*no*/
  height: 7px;/*no*/
  border-radius: 100%;
  -webkit-animation-fill-mode: both;
          animation-fill-mode: both;
  position: absolute;
  transform-origin: center 14px; /*no*/
}
@-webkit-keyframes wd-spin-wrap {
  50% {
    opacity: 0.3;
  }
  100% {
    opacity: 1;
  }
}
@keyframes wd-spin-wrap {
  50% {
    opacity: 0.3;
  }
  100% {
    opacity: 1;
  }
}

</style>
