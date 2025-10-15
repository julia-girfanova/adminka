<template>
  <div class="eventcard">
    <div class="pause">
      <img class="pause__icon" src="../public/vector.svg" />
    </div>
    <div class="card">
      <div class="card_condition">
        <div class="condition-text">Активный</div>
      </div>
      <div class="card_title">Событие мастер-класс</div>
      <div class="card_text">200 - 400 рублей</div>
    </div>
    <div class="settings">
      <img class="settings__icon" src="../public/more-fill.svg" />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.eventcard {
  border: 1px solid #bebfd1;
  border-radius: 15px;
  padding: 15px;
  display: inline-flex;
  width: calc(100% / 3 - 20px);
  height: 136px;
  box-sizing: border-box;
  margin-left: 20px;
  margin-bottom: 20px;
}
.pause {
  width: 35px;
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.pause__icon {
  width: 29px;
  height: 29px;
}
.card {
  margin-left: 15px;
}
.card_condition {
  width: 93px;
  height: 24px;
  border-radius: 26px;
  background-color: #e1ddfa;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 5px;
}
.condition-text {
  font-size: 12px;
  font-weight: 600;
  text-transform: uppercase;
  color: #6a56e6;
}
.card_title {
  font-size: 16px;
  font-weight: 500;
  color: #3d3a5b;
  line-height: 24px;
}
.card_text {
  font-size: 14px;
  font-weight: 400;
  color: #131330;
  line-height: 20px;
}
.settings {
  margin-left: auto;
  display: flex;
  width: 35px;
  height: 35px;
  align-items: center;
  justify-content: center;
}
.settings__icon {
  width: 25px;
  height: 25px;
}
</style>
