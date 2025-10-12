<template>
  <div class="header">
    <div class="header__text">Создать</div>
    <div class="header__id">
      <div class="header__id_avatar">
        <img class="header__id_icon" src="../public/user-line.svg" />
      </div>
      <div class="header__id_name">
        <div class="header-id">Ваш ID</div>
        <a class="header-name" href="#">Anton Ivanov</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.header {
  height: 70px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid #bebfd1;
  position: sticky;
  top: 0;
  background-color: white;
}
.header__id {
  display: flex;
  flex-direction: row;
  padding-right: 35px;
}
.header__id_avatar {
  width: 40px;
  height: 40px;
  border-radius: 12px;
  background-color: #f5f6f9;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 10px;
}
.header__id_icon {
  width: 20px;
  height: 20px;
}
.header-id {
  font-size: 12px;
  font-weight: 400;
  color: #bebfd1;
  display: flex;
  align-items: center;
  height: 50%;
}
.header-name {
  font-size: 15px;
  font-weight: 400;
  text-transform: uppercase;
  color: #000000;
  text-decoration: none;
  height: 50%;
  display: flex;
  align-items: center;
}
.header__text {
  font-size: 15px;
  margin-right: auto;
  font-weight: 700;
  padding-left: 35px;
  color: #2b2b33;
}
</style>
