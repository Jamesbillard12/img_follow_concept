<template>
  <div>
    <button @click="phaseOne">Phase One</button>
    <button @click="phaseTwo">Phase Two</button>
    <div class="home">
      <div
        v-for="(div) in divArr"
        :key="div.key"
        :id="div.id"
        :style="{
        top: div.top + '%',
        left: div.left + '%',
        transform: `scale(${div.width}, ${div.height})`,
        backgroundColor: div.bgCol,
        borderRadius: div.borderRadius + '%' 
        }"
        class="rand-div"
      ></div>
    </div>
    <div :class="{'home-overlap':true}">
      <div :class="{'img-div': true, 'show-hidden': showHidden}"></div>
      <div :class="{'text-div': true, 'show-hidden': showHidden}">
        <h1 v-if="title">{{title}}</h1>
        <p v-if="text">{{text}}</p>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  data() {
    return {
      divArr: [
        {
          id: "one",
          key: 1,
          bgCol: "white",
          top: 22,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "two",
          key: 2,
          bgCol: "white",
          top: 33,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "three",
          key: 3,
          bgCol: "white",
          top: 44,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },

        {
          id: "five",
          key: 5,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "six",
          key: 6,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "seven",
          key: 7,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "eight",
          key: 8,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        }
      ],

      elements: [],
      title: "Lorem ipsum dolor sit amet",
      text:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Aenean pharetra magna ac placerat vestibulum lectus. Morbi tincidunt ornare massa eget egestas. Amet consectetur adipiscing elit duis tristique sollicitudin nibh. Quis imperdiet massa tincidunt nunc pulvinar sapien et ligula. Tristique magna sit amet purus gravida quis blandit. Ultrices in iaculis nunc sed. Habitasse platea dictumst quisque sagittis purus sit amet volutpat. Id aliquet risus feugiat in ante metus. Augue eget arcu dictum varius duis at consectetur lorem donec. Dolor purus non enim praesent elementum facilisis leo. Nunc sed augue lacus viverra vitae congue eu consequat. Faucibus ornare suspendisse sed nisi. Integer eget aliquet nibh praesent tristique magna sit. Sociis natoque penatibus et magnis dis parturient montes nascetur ridiculus. Vehicula ipsum a arcu cursus. In ornare quam viverra orci sagittis eu.",
      showHidden: false
    };
  },
  methods: {
    phaseOne() {
      this.divArr = [
        {
          id: "one",
          key: 1,
          bgCol: "rgba(255,255,255,0.5)",
          top: 20,
          left: 5,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "two",
          key: 2,
          bgCol: "rgba(255,255,255,0.5)",
          top: 20,
          left: 15,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "three",
          key: 3,
          bgCol: "rgba(255,255,255,0.5)",
          top: 20,
          left: 25,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "five",
          key: 5,
          bgCol: "rgba(255,255,255,0.5)",
          top: 50,
          left: 5,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "six",
          key: 6,
          bgCol: "rgba(255,255,255,0.5)",
          top: 50,
          left: 15,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "seven",
          key: 7,
          bgCol: "rgba(255,255,255,0.5)",
          top: 50,
          left: 25,
          width: 1,
          height: 1,
          borderRadius: 0
        },
        {
          id: "eight",
          key: 8,
          bgCol: "rgba(255,255,255,0.5)",
          top: 35,
          left: 70,
          width: 4,
          height: 2,
          borderRadius: 0
        }
      ];

      this.showHidden = true;
    },
    phaseTwo() {
      this.divArr = [
        // {
        //   id: "zero",
        //   key: 0,
        //   bgCol: "white",
        //   top: 11,
        //   left: this.getRandomNum(90),
        //   width: 0.015,
        //   height: 0.015,
        //   borderRadius: this.getRandomNum(50)
        // },
        {
          id: "one",
          key: 1,
          bgCol: "white",
          top: 22,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "two",
          key: 2,
          bgCol: "white",
          top: 33,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "three",
          key: 3,
          bgCol: "white",
          top: 44,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        // {
        //   id: "four",
        //   key: 4,
        //   bgCol: "white",
        //   top: 55,
        //   left: this.getRandomNum(90),
        //   width: 0.015,
        //   height: 0.015,
        //   borderRadius: this.getRandomNum(50)
        // },
        {
          id: "five",
          key: 5,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "six",
          key: 6,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "seven",
          key: 7,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        },
        {
          id: "eight",
          key: 8,
          bgCol: "white",
          top: 66,
          left: this.getRandomNum(90),
          width: 0.015,
          height: 0.015,
          borderRadius: this.getRandomNum(50)
        }
      ];
      this.showHidden = false;
    },
    getRandomNum(num) {
      let randNum = Math.floor(Math.random() * Math.floor(num));
      if (randNum < 1) {
        randNum = 1;
      }
      return randNum;
    }
  },

  components: {
    HelloWorld
  }
};
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  width: 100vw;
  height: 50vh;
  background-color: black;
  background-image: url("http://www.script-tutorials.com/demos/360/images/twinkling.png"),
    url("../assets/twinkling-stars.png");
  background-size: auto, contain;
  box-sizing: border-box;
  -moz-animation: move-twink-back 200s linear infinite;
  -ms-animation: move-twink-back 200s linear infinite;
  -o-animation: move-twink-back 200s linear infinite;
  -webkit-animation: move-twink-back 200s linear infinite;
  animation: move-twink-back 200s linear infinite;
}
.rand-div {
  position: absolute;
  width: 10%;
  height: 30%;
  transition-property: transform, left, top, border-radius, background-color;
  transition-duration: 1s;
  transition-timing-function: ease-in-out;
}
.home-overlap {
  position: absolute;
  top: 106px;
  width: 100vw;
  height: 50vh;
  background-size: contain;
  transition: opacity 1s ease-in-out;
  background-image: none;
}

.img-div {
  position: absolute;
  width: 30%;
  height: 61%;
  top: 20%;
  left: 5%;
  background-image: url("../assets/christophe-dutour-756565-unsplash.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  opacity: 0;
  transition: opacity 0.2s ease-in-out;
}
.text-div {
  text-align: left;
  position: absolute;
  width: 40%;
  height: 61%;
  top: 20%;
  left: 55%;
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
  p,
  h1 {
    padding-left: 10px;
  }
}

.show-hidden {
  opacity: 1;
  transition: opacity 0.5s 1s ease-in-out;
}
@keyframes move-twink-back {
  from {
    background-position: 0 0, 0 0;
  }
  to {
    background-position: -10000px 5000px, 0 0;
  }
}
@-webkit-keyframes move-twink-back {
  from {
    background-position: 0 0, 0 0;
  }
  to {
    background-position: -10000px 5000px, 0 0;
  }
}
@-moz-keyframes move-twink-back {
  from {
    background-position: 0 0, 0 0;
  }
  to {
    background-position: -10000px 5000px, 0 0;
  }
}
@-ms-keyframes move-twink-back {
  from {
    background-position: 0 0, 0 0;
  }
  to {
    background-position: -10000px 5000px, 0 0;
  }
}
</style>
