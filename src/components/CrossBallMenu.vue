<template>
  <header>
    <img src="@/assets/images/header/logo.svg" alt="" class="crossball-logo" />
    <nav>
      <ul class="header-menu">
        <li><a href="">Расписание</a></li>
        <li><a href="">Игровые отчёты</a></li>
        <li><a href="">Статистика</a></li>
        <li>
          <a href="" class="more"
            >Ещё <img src="@/assets/images/misc/arrow-down.svg" alt=""
          /></a>
        </li>
      </ul>
    </nav>
    <div class="dropdawn-season">
      <vueSelect></vueSelect>
    </div>
    <img
      src="@/assets/images/header/person.jpg"
      alt=""
      class="persona-icon"
      width="40"
      height="40"
    />
    <div class="bag">
      <img src="@/assets/images/header/bag.svg" alt="" />
    </div>
  </header>
</template>

<script>
import vueSelect from './VueSelect.vue'
export default {
  components: {
    vueSelect
  }
}
</script>

<style scoped lang="scss">
header {
  padding-left: 40px;
  padding-right: 40px;
  display: flex;
  column-gap: 40px;
  align-items: center;
  justify-content: space-between;
  height: 80px;
  box-shadow: 0 2px 4px #e9e9e9;
}
.bag {
  position: relative;
  width: 21px;
  height: 30px;
}
.bag::after {
  display: flex;
  align-items: center;
  justify-content: center;
  content: '1';
  font-size: 12px;
  text-align: center;
  width: 16px;
  height: 16px;
  border-radius: 20px;
  position: absolute;
  top: 14px;
  left: 10px;
  background-color: #86e3ce;
  color: white;
}

.crossball-logo {
}
.header-menu {
  display: flex;
  list-style: none;
  column-gap: 50px;
}
.header-menu li a {
  color: black;
  text-decoration: none;
}

.header-menu .more {
  margin-left: 20px;
}
.dropdawn-season {
  width: 70px;
  height: 40px;
  margin-right: 70px;
}
.persona-icon {
  margin-right: 70px;
  border-radius: 40px;
  object-fit: cover;
  border: 2px solid #5a60e7;
}
.bag {
}
</style>
