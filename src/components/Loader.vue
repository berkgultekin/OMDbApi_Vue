<template>
  <div class="loader" :class="clas">
    <div class="loader__wrappeer">
      <img class="loader__popcorn" src="../assets/loader-popcorn.svg"/>
      <img class="loader__crumb crumb1" src="../assets/loader-crumb1.svg"/>
      <img class="loader__crumb crumb2" src="../assets/loader-crumb2.svg"/>
      <img class="loader__crumb crumb3" src="../assets/loader-crumb1.svg"/>
      <img class="loader__crumb crumb4" src="../assets/loader-crumb2.svg"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "Loader",
  props: {
    clas: String
  }
};
</script>

<style lang="scss" scoped>
@keyframes show {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.loader {
  position: relative;
  width: 100%;
  height: 100%;
  animation: show 2s;
  align-self: center;
  justify-self: center;

  &.search {
    min-height: 30rem;
    flex-basis: 100%;
  }

  &__wrappeer {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }

  &__popcorn {
    height: 10rem;
    width: auto;
  }

  &__crumb {
    position: absolute;
    height: 1.7rem;

    @keyframes jump {
      0% {
        transform: translateY(0rem) rotate(0deg);
      }

      50% {
        transform: translateY(-3rem) rotate(180deg);
      }

      100% {
        transform: translateY(0rem) rotate(360deg);
      }
    }

    &.crumb1 {
      left: -12%;
      top: 0%;
      animation: jump 0.7s 0.5s both infinite;
    }

    &.crumb2 {
      left: 18%;
      top: -20%;
      animation: jump 0.8s 0.1s both infinite;
    }

    &.crumb3 {
      left: 55%;
      top: -23%;
      animation: jump 0.5s 0.2s both infinite;
    }

    &.crumb4 {
      left: 93%;
      top: 0%;
      animation: jump 0.5s both infinite;
    }
  }
}
</style>