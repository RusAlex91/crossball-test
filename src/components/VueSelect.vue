<template>
  <div class="v-select">
    <div class="title" @click="optionsVisible = !optionsVisible">
      <span v-if="!optionsVisible && selected == null">
        <img src="../assets/images/header/select-ball.svg" alt=""
      /></span>
      <img :src="selected" alt="" />
      <img src="../assets/images/misc/arrow-down.svg" alt="" />
    </div>
    <div class="options" v-if="optionsVisible">
      <p v-for="option in options" :key="option.id">
        <img :src="option.imageUrl" alt="" @click="selectOption(option)" />
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      optionsVisible: false,

      options: [
        {
          id: 1,
          imageUrl: 'https://via.placeholder.com/35x35/81ffd5'
        },
        { id: 2, imageUrl: 'https://via.placeholder.com/35x35' },
        {
          id: 3,
          imageUrl: require('@/assets/images/header/select-ball.svg')
        }
      ],
      selected: null
    }
  },
  methods: {
    selectOption (option) {
      // emit
      this.selected = option.imageUrl
      this.optionsVisible = false
      this.firstTime = false
    }
  }
}
</script>

<style scoped lang="scss">
.v-select {
  width: 70px;
  height: 40px;
  background-color: #fff;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.title {
  display: flex;
  column-gap: 5px;
  align-items: center;
  justify-content: center;
}
.options {
  position: relative;
  top: 90px;
}
</style>
