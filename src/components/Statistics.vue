<template>
  <div class="season-stat-wrapper">
    <div class="achievements">
      <div class="achivement-group-wrapper">
        <div class="achievement-group">
          <achievement :isDisabled="false" :counter="5"></achievement>
          <achievement :isDisabled="false" :counter="5"></achievement>
          <achievement :isDisabled="false" :counter="99"></achievement>
          <div class="achievement-group-disabled">
            <achievement :isDisabled="true" :counter="0"></achievement>
            <achievement :isDisabled="true" :counter="0"></achievement>
          </div>
        </div>
      </div>
      <hr />
      <div class="achievement-group">
        <achievement :isDisabled="false" :counter="0"></achievement>
        <achievement :isDisabled="false" :counter="0"></achievement>
        <achievement :isDisabled="false" :counter="0"></achievement>
        <achievement :isDisabled="false" :counter="0"></achievement>
        <achievement :isDisabled="false" :counter="0"></achievement>
      </div>
    </div>
    <div class="season">
      <div class="season-time-pick">
        <span class="selected">Все сезоны</span>
        <span>Сезон 2020/21</span>
      </div>
      <div class="season-stat">
        <div class="games"><span>Игры</span>{{ totalGameCount }}</div>
        <div class="goal"><span>Гол</span>{{ totalGoal }}</div>
        <div class="pass"><span>Пас</span>{{ totalPass }}</div>
        <div class="goal-pass"><span>Гол+Пас</span>{{ totalPassGoalSum }}</div>
      </div>
    </div>
    <div class="statistics-media">
      <a href="https://www.facebook.com/">
        <img src="@/assets/images/misc/facebook.svg" alt="" />
      </a>
      <a href="https://www.vk.com/">
        <img src="@/assets/images/misc/vk.svg" alt="" />
      </a>
      <a href="#">
        <img src="@/assets/images/misc/share.svg" alt="" />
      </a>
    </div>
  </div>
</template>

<script>
import Achievement from './Achivement.vue'
export default {
  components: {
    Achievement
  },
  data () {
    return {
      seasons: [
        {
          seasonStartYear: 2015,
          gamesAmount: 5,
          goal: 3,
          pass: 3,
          raiting: 89.11
        },
        {
          seasonStartYear: 2019,
          gamesAmount: 4,
          goal: 2,
          pass: 1,
          raiting: 49.3
        },
        {
          seasonStartYear: 2018,
          gamesAmount: 6,
          goal: 5,
          pass: 5,
          raiting: 99.42
        },
        {
          seasonStartYear: 2017,
          gamesAmount: 1,
          goal: 1,
          pass: 5,
          raiting: 45.8
        },
        {
          seasonStartYear: 2016,
          gamesAmount: 8,
          goal: 9,
          pass: 12,
          raiting: 77.4
        }
      ],
      totalGoal: 0,
      totalGameCount: 0,
      totalPass: 0,
      totalPassGoalSum: 0
    }
  },
  methods: {
    setStat () {
      const seasons = this.seasons
      // eslint-disable-next-line no-unused-vars
      let totalGoalTemp = 0
      // eslint-disable-next-line no-unused-vars
      let totalGameCountTemp = 0
      // eslint-disable-next-line no-unused-vars
      let totalPassTemp = 0

      seasons.forEach(season => {
        totalGoalTemp = season.goal + totalGoalTemp
        totalGameCountTemp = season.gamesAmount + totalGameCountTemp
        totalPassTemp = season.pass + totalPassTemp
      })
      this.totalGoal = totalGoalTemp
      this.totalGameCount = totalGameCountTemp
      this.totalPass = totalPassTemp
      this.totalPassGoalSum = totalPassTemp + totalGoalTemp
    }
  },
  mounted () {
    this.setStat()
  }
}
</script>

<style scoped lang="scss">
.season-stat-wrapper {
  display: flex;
  width: 1050px;
  height: 190px;
  margin-top: 20px;
  margin-left: 50px;
  background: url(../assets/images/personal/achivement/pattern.svg) no-repeat
      98% center,
    linear-gradient(
      238.37deg,
      rgba(90, 96, 231, 0.35) 6.34%,
      rgba(30, 30, 40, 0) 103.77%
    ),
    #2c2c2c;
}
.achievements {
  display: flex;
  width: 300px;
  flex-direction: column;
}
.achievement-group-wrapper {
  display: flex;
}

.achievement-group {
  /* .achivment-group__disabled */
  display: flex;
  border: 1px solid tomato;
  column-gap: 10px;
}

hr {
  width: 100%;
}
.achievement-group-disabled {
  margin-left: 60px;
  display: flex;
  column-gap: 10px;
}
.season {
  margin-left: 30px;
}
.season-time-pick {
  display: flex;
  align-items: center;
  border: 1px solid #5a60e7;
  width: 400px;
  height: 85px;
  font-size: 16px;
  span {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 200px;
    height: 30px;
  }
}
.selected {
  background: #5a60e7;
}
.season-stat {
  display: flex;
}
.games {
  width: 95px;
  height: 75px;
  background: linear-gradient(
      238.37deg,
      rgba(90, 96, 231, 0.35) 6.34%,
      rgba(30, 30, 40, 0) 103.77%
    ),
    #2c2c2c;
  span {
    font-size: 30px;
    color: #ff795b;
  }
}
.goal {
  width: 95px;
  height: 75px;
  background: linear-gradient(
      238.37deg,
      rgba(90, 96, 231, 0.35) 6.34%,
      rgba(30, 30, 40, 0) 103.77%
    ),
    #2c2c2c;
  span {
    font-size: 30px;
    color: #ff795b;
  }
}
.pass {
  width: 95px;
  height: 75px;
  background: linear-gradient(
      238.37deg,
      rgba(90, 96, 231, 0.35) 6.34%,
      rgba(30, 30, 40, 0) 103.77%
    ),
    #2c2c2c;
  span {
    font-size: 30px;
    color: #ff795b;
  }
}
.goal-pass {
  width: 95px;
  height: 75px;
  background: linear-gradient(
      238.37deg,
      rgba(90, 96, 231, 0.35) 6.34%,
      rgba(30, 30, 40, 0) 103.77%
    ),
    #2c2c2c;
  span {
    font-size: 30px;
    color: #ff795b;
  }
}
.statistics-media {
}
</style>
