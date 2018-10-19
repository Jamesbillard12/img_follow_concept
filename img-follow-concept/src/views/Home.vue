<template>
  <div @mouseout="onMouseOut" @mousemove="getMouse" class="home">
    <div
      v-for="(div) in divArr"
      :key="div.key"
      :id="div.id"
      :style="{
        top: div.top + 'px',
        left: div.left + 'px',
        backgroundColor: div.bgCol, 
        borderRadius: 5 + '%'}"
      class="rand-div"
    ></div>
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
          id: "zero",
          key: 0,
          bgCol: "pink",
          top: 150,
          left: 950,
          offsetX: 100,
          offsetY: 100
        },
        {
          id: "one",
          key: 1,
          bgCol: "red",
          top: 250,
          left: 450,
          offsetX: 20,
          offsetY: 40
        },
        {
          id: "two",
          key: 2,
          bgCol: "blue",
          top: 100,
          left: 600,
          offsetX: 30,
          offsetY: 50
        },
        {
          id: "three",
          key: 3,
          bgCol: "green",
          top: 250,
          left: 850,
          offsetX: 40,
          offsetY: 60
        },
        {
          id: "zero",
          key: 4,
          bgCol: "pink",
          top: 300,
          left: 900,
          offsetX: 100,
          offsetY: 100
        },
        {
          id: "one",
          key: 5,
          bgCol: "red",
          top: 150,
          left: 550,
          offsetX: 20,
          offsetY: 40
        },
        {
          id: "two",
          key: 6,
          bgCol: "blue",
          top: 200,
          left: 500,
          offsetX: 30,
          offsetY: 50
        },
        {
          id: "three",
          key: 7,
          bgCol: "green",
          top: 200,
          left: 1000,
          offsetX: 40,
          offsetY: 60
        }
      ],

      elements: []
    };
  },
  methods: {
    getMouse(e) {
      setInterval(this.followMouse(e.pageX, e.pageY), 50);
    },

    followMouse(x, y) {
      for (let i = 0; i < this.divArr.length; i++) {
        let oriY = this.divArr[i].top > y;
        let oriX = this.divArr[i].left > x;
        let distX = y - this.divArr[i].top;
        let distY = x - this.divArr[i].left;

        this.divArr[i].top = this.divArr[i].top + distX;
        this.divArr[i].left = this.divArr[i].left + distY;
      }
    },

    onMouseOut() {
      this.divArr = [
        {
          id: "zero",
          key: 0,
          bgCol: "pink",
          top: 150,
          left: 950,
          offsetX: 100,
          offsetY: 100
        },
        {
          id: "one",
          key: 1,
          bgCol: "red",
          top: 250,
          left: 450,
          offsetX: 20,
          offsetY: 40
        },
        {
          id: "two",
          key: 2,
          bgCol: "blue",
          top: 100,
          left: 600,
          offsetX: 30,
          offsetY: 50
        },
        {
          id: "three",
          key: 3,
          bgCol: "green",
          top: 250,
          left: 850,
          offsetX: 40,
          offsetY: 60
        },
        {
          id: "zero",
          key: 4,
          bgCol: "pink",
          top: 300,
          left: 900,
          offsetX: 100,
          offsetY: 100
        },
        {
          id: "one",
          key: 5,
          bgCol: "red",
          top: 150,
          left: 550,
          offsetX: 20,
          offsetY: 40
        },
        {
          id: "two",
          key: 6,
          bgCol: "blue",
          top: 200,
          left: 500,
          offsetX: 30,
          offsetY: 50
        },
        {
          id: "three",
          key: 7,
          bgCol: "green",
          top: 200,
          left: 1000,
          offsetX: 40,
          offsetY: 60
        }
      ];
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
}
.rand-div {
  position: absolute;
  width: 100px;
  height: 100px;
  transition: all 1s;
}
</style>
