<template>
  <header class="header">
    <div class="header__images">

    </div>
    <div class="header__content">
      <div class="header__col">
        <h1 class="header__title">
          <span>Open Movie</span>
          <span>Database</span>
        </h1>
        <form class="search-bar" v-on:submit.prevent="changeLocation">
          <input type="text" v-model="filmName" class="search-bar__input"/>
          <button class="search-bar__btn btn">Search</button>
        </form>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",

  data() {
    return {
      filmName: ""
    };
  },

  methods: {
    changeLocation() {
      if (this.filmName != "") {
        window.location = `./search#${this.filmName}&`;
      } else {
        window.location = `./search`;
      }
    }
  }
};
</script>


<style lang="scss" scoped>
.header {
  position: relative;
  display: flex;
  height: 100vh;
  width: 100%;
  overflow: hidden;

  &__bg-title {
    position: absolute;
    opacity: 0.04;
    width: 100%;
    z-index: -1;
    top: 7%;
  }

  &__images {
    position: relative;
    width: 38%;
  }

  &__popcorn {
    width: 107%;
    position: absolute;
    left: -13.5%;
    bottom: -7%;
    animation: popcorn 0.5s 3s both linear;
  }

  &__image {
    width: 100%;
  }

  &__fall {
    width: 15%;
    top: 25%;
    left: 30%;
    height: auto;
    position: absolute;
    z-index: 3;
    animation: fall 1.3s 3.8s both;
  }

  &__glass3d {
    width: 107%;
    position: absolute;
    bottom: 23%;
    left: 20%;
    transform: rotate(-58deg);
    z-index: 2;
  }

  &__content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-left: 8%;
    animation: show-right 1s 0.6s both linear;
  }

  &__title {
    font-family: "Bebas Neue", cursive;
    font-size: 20rem;
    font-weight: 400;
    text-shadow: -0.5rem 0 0 #f40048;
    letter-spacing: 0.2rem;
    line-height: 100%;
    margin: 2rem 0;
    transition: 0.3s;

    & span {
      display: block;
    }
  }

  &__subtitle {
    font-family: "Montserrat", sans-serif;
    text-transform: uppercase;
    font-size: 3.5rem;
    margin: 0;
  }
}

.search-bar {
  width: 100%;

  &__input {
    height: 8.2rem;
    width: 70%;
    border-radius: 4rem;
    background: transparent;
    border: 1px solid white;
    background-image: url("../assets/search1.svg");
    background-repeat: no-repeat;
    background-position: 2.5rem;
    background-size: 3rem;
    padding-left: 8rem;
    font-family: "Montserrat", sans-serif;
    font-size: 2.2rem;
    animation: show-input 1s 1.6s both linear;
    color: white;
  }

  &__btn {
    margin-left: 2rem;
    border-radius: 4.1rem;
    animation: show-btn 1s 2.6s both linear;
    padding: 2.8rem 5.4rem;
  }
}

@keyframes show-input {
  0% {
    max-width: 8.2rem;
  }
  100% {
    max-width: 100%;
  }
}

@keyframes show-btn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes show-right {
  0% {
    transform: translateX(2rem);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

@keyframes popcorn {
  0% {
    transform: rotate(0deg);
  }
  20% {
    transform: rotate(5deg);
  }
  40% {
    transform: rotate(-5deg);
  }
  60% {
    transform: rotate(3deg);
  }
  80% {
    transform: rotate(-3deg);
  }
  100% {
    transform: rotate(0deg);
  }
}

@keyframes fall {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(100vh);
  }
}

@media (max-width: 1600px) {
  .header {
    &__title {
      font-size: 15rem;
    }
  }
  .search-bar {
    &__input {
      height: 6rem;
      background-size: 2.5rem;
      background-position: 1.8rem;
      width: 70%;
      padding-left: 6rem;
      font-size: 1.8rem;
    }

    &__btn {
      font-size: 1.8rem;
      padding: 2rem 2.5rem;
    }
  }

  @keyframes show-input {
    0% {
      max-width: 6rem;
    }
    100% {
      max-width: 100%;
    }
  }
}

@media (max-width: 1440px) {
  .header {
    &__images {
      width: 40%;
    }

    &__content {
      width: 60%;
      align-items: flex-start;
    }
  }
}

@media (max-width: 1200px) {
  .header {
    &__title {
      font-size: 14rem;
      text-shadow: -0.3rem 0 0 #f40048;
      margin: 1rem 0;
    }

    &__subtitle {
      font-size: 1.8rem;
    }
  }

  .search-bar {
    &__input {
      height: 5rem;
      background-size: 1.5rem;
      background-position: 1.75rem;
      width: 60%;
      padding-left: 4rem;
    }

    &__btn {
      padding: 1.5rem 2rem;
    }
  }

  @keyframes show-input {
    0% {
      max-width: 5rem;
    }
    100% {
      max-width: 100%;
    }
  }
}

@media (max-width: 1024px) {
  .header {
    flex-direction: column-reverse;

    &__images {
      width: 60%;
      height: 50vh;
      margin: 0 auto;
    }

    &__popcorn {
      width: 100%;
      left: 0;
    }

    &__content {
      width: 100%;
      padding-left: 0;
      align-items: center;
    }

    &__title {
      text-align: center;
    }

    &__subtitle {
      text-align: center;
    }
  }
  .search-bar {
    display: flex;
    justify-content: center;

    &__input {
      animation: none;
    }

    &__btn {
      animation: none;
    }
  }
}

@media (max-width: 600px) {
  .header {
    flex-direction: column-reverse;

    &__title {
      font-size: 7rem;
      text-shadow: -0.1rem 0 0 #f40048, 0.1rem 0 0 #f40048;
    }

    &__subtitle {
      font-size: 1.5rem;
    }

    &__images {
      width: 80%;
    }

    &__bg-title {
      top: 0;
    }
  }

  .search-bar {
    &__input {
      height: 4rem;
      background-position: 1.2rem;
      width: 50%;
    }

    &__btn {
      font-size: 1.4rem;
      padding: 1.2rem 2rem;
      margin-left: 1rem;
    }
  }
}

@media (max-height: 600px) {
  .header {
    &__images {
      display: none;
    }

    &__content {
      height: 100vh;
    }
  }
}
</style>
