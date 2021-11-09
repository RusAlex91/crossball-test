<template>
  <div class="table">
    <div class="table-head">
      <span @click="preSort()">Сезон</span>
      <span @click="sortByAmount()">Кол-во игр</span>
      <span @click="sortByGoal()">Гол</span>
      <span @click="sortByPass()">Пас</span>
      <span @click="sortByGoalPass()">Гол+пас</span>
      <span @click="sortByRaiting()">Рейтинг</span>
    </div>
    <div
      class="table-body"
      v-for="season in seasons"
      :key="season.seasonStartYear"
    >
      <span
        >Сезон {{ season.seasonStartYear + 1 }}/{{
          season.seasonStartYear
        }}</span
      >
      <span>{{ season.gamesAmount }}</span>
      <span>{{ season.goal }}</span>
      <span>{{ season.pass }}</span>
      <span>{{ season.goal + season.pass }}</span>
      <span>{{ season.raiting }}</span>
    </div>
  </div>
</template>

<script>
export default {
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
      sorted: false
    }
  },
  methods: {
    preSort () {
      const seasons = this.seasons
      seasons.sort(function (a, b) {
        return b.seasonStartYear - a.seasonStartYear
      })
      this.seasons = seasons
    },
    sortByAmount (sortName) {
      const seasons = this.seasons
      if (this.sorted === false) {
        seasons.sort(function (a, b) {
          return b.gamesAmount - a.gamesAmount
        })
        this.sorted = true
      } else if (this.sorted === true) {
        seasons.sort(function (a, b) {
          return a.gamesAmount - b.gamesAmount
        })
        this.sorted = false
      }

      this.seasons = seasons
    },
    sortByGoal (sortName) {
      const seasons = this.seasons
      if (this.sorted === false) {
        seasons.sort(function (a, b) {
          return b.goal - a.goal
        })
        this.sorted = true
      } else if (this.sorted === true) {
        seasons.sort(function (a, b) {
          return a.goal - b.goal
        })
        this.sorted = false
      }

      this.seasons = seasons
    },
    sortByPass (sortName) {
      const seasons = this.seasons
      if (this.sorted === false) {
        seasons.sort(function (a, b) {
          return b.pass - a.pass
        })
        this.sorted = true
      } else if (this.sorted === true) {
        seasons.sort(function (a, b) {
          return a.pass - b.pass
        })
        this.sorted = false
      }

      this.seasons = seasons
    },
    sortByRaiting (sortName) {
      const seasons = this.seasons
      if (this.sorted === false) {
        seasons.sort(function (a, b) {
          return b.raiting - a.raiting
        })
        this.sorted = true
      } else if (this.sorted === true) {
        seasons.sort(function (a, b) {
          return a.raiting - b.raiting
        })
        this.sorted = false
      }

      this.seasons = seasons
    },
    sortByGoalPass (sortName) {
      const seasons = this.seasons
      if (this.sorted === false) {
        seasons.sort(function (a, b) {
          debugger
          const gpa = a.goal + a.pass
          const gpb = b.pass + b.goal

          return gpb - gpa
        })
        this.sorted = true
      } else if (this.sorted === true) {
        seasons.sort(function (a, b) {
          debugger
          const gpa = a.goal + a.pass
          const gpb = b.pass + b.goal

          return gpa - gpb
        })
        this.sorted = false
      }
    }
  },
  created () {
    this.preSort()
  }
}
</script>

<style scoped>
.table-head {
  display: grid;
  grid-auto-columns: 1fr;
  grid-template-columns: 1.9fr 1.1fr 0.8fr 0.8fr 0.8fr 0.8fr;
  grid-template-rows: 1fr;
  gap: 0px 0px;
  grid-template-areas: '. . . . . .';
}

.table-body {
  display: grid;
  grid-auto-columns: 1fr;
  grid-template-columns: 1.9fr 1.1fr 0.8fr 0.8fr 0.8fr 0.8fr;
  grid-template-rows: 1fr;
  gap: 0px 0px;
  grid-template-areas: '. . . . . .';
}
</style>
