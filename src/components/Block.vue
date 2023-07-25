<template>
  <div v-if="showBlock" class="block" @click="endGame">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      reactionTime: null,
      timer: null,
    };
  },
  methods: {
    endGame() {
      this.showBlock = false;
      this.result = this.reactionTime;
      this.$emit("end", this.reactionTime);
      clearInterval(this.timer);
    },
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    }, [this.delay]);
  },
   
};
</script>

<style>
.block {
  width: 400px;
  height: 200px;
  border-radius: 16px;
  background-color: rgb(41, 185, 185);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px;
  font-size: 20px;
  font-weight: bold;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
</style>
