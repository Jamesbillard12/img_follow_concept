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
        { id: "zero", key: 0, bgCol: "pink", top: 200, left: 900 },
        { id: "one", key: 1, bgCol: "red", top: 300, left: 500 }
      ],

      elements: []
    };
  },
  methods: {
    getMouse(e) {
      this.followMouse(e.pageX, e.pageY);
    },
    followMouse(x, y) {
      for (let i = 0; i < this.divArr.length; i++) {
        var distX = y - this.divArr[i].top;
        var distY = x - this.divArr[i].left;
        this.divArr[i].top += distX;
        this.divArr[i].left += distY;
      }
    },

    onMouseOut() {
      this.divArr = [
        { id: "zero", key: 0, bgCol: "pink", top: 200, left: 900 },
        { id: "one", key: 1, bgCol: "red", top: 300, left: 500 }
      ];
      console.log(this.divArr);
    }
  },
  created() {
    for (let div of this.divArr) {
      this.elements.push(document.getElementById(div.id));
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
