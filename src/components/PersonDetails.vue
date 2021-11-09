<template>
  <div class="personal-details">
    <div class="personal-details-head">
      <div class="head-info">
        <div class="head-image-wrapper">
          <img
            src="@/assets/images/personal/details/person.jpg"
            alt=""
            class="head-person"
          />
          <span class="fill-radius"></span>
        </div>
        <div class="head-stat">
          <span class="head-stat-rep">89.40 <span>999</span></span>
          <span class="head-stat-name">Елишакашвили Михо</span>
        </div>
      </div>

      <span class="presonal-details-head__edit">
        <img src="@/assets/images/personal/details/pen.svg" alt="" />
        <img
          src="@/assets/images/personal/details/line.svg"
          alt=""
        />Редактировать</span
      >
    </div>
    <div class="personal-details-body">
      <div class="statistics">
        <div class="statistics__category">
          <img
            src="@/assets/images/personal/details/statPersonal.svg"
            alt=""
            class="statisctics-portfolio-img"
          />
          <span>Статистика</span>
        </div>
        <div class="statistics__sub-category">
          <span>Футбол</span>
          <span>Баскетбол</span>
          <span>Волейбол</span>
        </div>
      </div>
      <div class="upcoming-games">
        <img src="@/assets/images/personal/details/upcoming-games.svg" alt="" />
        <span>Ближайшие игры</span>
      </div>
      <div class="game-reports">
        <img src="@/assets/images/personal/details/gameReports.svg" alt="" />
        <span>Игровые отчёты</span>
      </div>
      <div class="order-history">
        <img src="@/assets/images/personal/details/orderHistory.svg" alt="" />
        <span>Ближайшие игры</span>
      </div>
    </div>
    <div class="personal-details-footer">
      <div class="logout">
        <img src="@/assets/images/personal/details/logout.svg" alt="" />
        <span>Выйти</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped lang="scss">
.personal-details {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  row-gap: 50px;
  width: 300px;
  height: 800px;
  background-color: #ffffff;
  box-shadow: 2px 2px 8px 0px rgba(34, 60, 80, 0.2);
}
.personal-details-head {
  display: flex;
  flex-direction: column;
  row-gap: 50px;
  background: linear-gradient(238.37deg, #5a60e759 0.34%, #1e1e2800 103.77%),
    #2c2c2c;
  border-radius: 5px;
  height: 200px;
}
.presonal-details-head__edit {
  margin-left: 20px;
  color: #acaff3;
}
.head-info {
  margin-top: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}
.head-stat {
  display: flex;
  flex-direction: column;
}
.head-stat-name {
  width: 140px;
  font-weight: 400;
  line-height: 22px;
}
.head-person {
  border-radius: 50px;
  object-fit: cover;
  width: 70px;
  height: 70px;
  z-index: 2;
  display: block;
}
.head-image-wrapper {
  position: relative;
  width: 70px;
  height: 70px;
  z-index: 3;
  margin: 10px;
}
.fill-radius {
  position: absolute;
  top: 0px;
  z-index: -1;
  display: block;
  width: 74px;
  height: 74px;
  border-radius: 40px;
  right: -2px;
  top: -2px;
  background: linear-gradient(200deg, transparent 50%, #ff795b 50%),
    linear-gradient(90deg, #c4c4c4 50%, #ff795b 50%);
}
.head-stat-rep {
  position: relative;
  font-size: 30px;
}
.head-stat-rep span {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 12px;
  width: 40px;
  height: 15px;
  border-radius: 20px;
  position: absolute;
  top: -2px;
  left: 20px;
  background-color: #ffffff;
  color: #5a60e7;
}
.personal-details-body {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: 16px;
}

.personal-details-body img {
  margin-right: 10px;
}
.statistics {
  /* .statistics__sub-category */

  width: 200px;
  display: flex;
  flex-direction: column;

  &__category {
    display: flex;
    align-items: center;

    width: 200px;
    height: 35px;
  }

  &__sub-category {
    display: flex;
    flex-direction: column;
    width: 200px;
    span {
      height: 35px;
    }
  }
}
.statisctics-portfolio-img {
}
.upcoming-games {
  display: flex;
  align-items: center;
  width: 200px;
}
.game-reports {
  display: flex;
  align-items: center;
  width: 200px;
}
.order-history {
  display: flex;
  align-items: center;
  width: 200px;
}
.personal-details-footer {
  display: flex;
  align-items: center;
  justify-content: center;
}
.logout {
  display: flex;
  align-items: center;
  width: 200px;
}
</style>
