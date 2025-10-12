<template>
  <div class="list_controls">
    <div class="platform__choise">
      <div class="platform__choise_name">
        <div class="platform__choise_text">Выбраны все площадки</div>
        <div class="list_arrow">
          <img src="../public/checkmark_16.svg" />
        </div>
      </div>
      <div class="platform__choise_active">
        <div class="platform__choise_text">Активный</div>
        <img class="list_arrow" src="../public/checkmark_16.svg" />
      </div>
    </div>
    <div class="platform__search">
      <img class="platform__search_icon" src="../public/search-outline.svg" />
      <div class="platform__search_hint">Поиск по названию билета</div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.list_controls {
  display: flex;
  justify-content: space-between;
  padding: 10px 0px;
  margin-left: 20px;
  margin-right: 20px;
}
.platform__choise {
  display: flex;
  gap: 15px;
}
.platform__choise_name {
  border: 1px solid #bebfd1;
  border-radius: 16px;
  width: 350px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.platform__choise_text {
  padding: 14px 0px 14px 16px;
  margin-right: 10px;
  color: #111127;
}
.list_arrow {
  width: 16px;
  height: 16px;
  margin-right: 18px;
}
.platform__search {
  width: 350px;
  background-color: #f4f4f6;
  border-radius: 12px;
  display: flex;
  align-items: center;
}
.platform__choise_active {
  border: 1px solid #bebfd1;
  border-radius: 16px;
  width: 220px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.platform__search_icon {
  margin-left: 12px;
}
.platform__search_hint {
  padding: 14px 0;
  margin-left: 8px;
  color: #73737a;
}
</style>
