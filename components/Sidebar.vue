<template>
  <div class="sidebar">
    <div class="logo">
      <img src="../public/logo-full.svg" />
    </div>
    <div class="menu">
      <div class="list-item">
        <div class="element">
          <div class="icon">
            <img src="../public/home-outline.svg" />
          </div>
          <div class="text">Главная</div>
        </div>
      </div>
      <div class="list-item">
        <div class="element">
          <div class="icon">
            <img src="../public/museum-outline.svg" />
          </div>
          <div class="text">Площадки</div>
        </div>
      </div>
      <div class="list-item">
        <div class="element">
          <div class="icon">
            <img src="../public/consultant-outline.svg" />
          </div>
          <div class="text">Контроль</div>
        </div>
      </div>
      <div
        @click="toggle_dropdown('tickets')"
        class="list-item"
        :class="[is_dropdown_opened('tickets') ? 'list-item_active' : '']"
      >
        <div class="element">
          <div class="icon">
            <img src="../public/tiket-outline.svg" />
          </div>
          <div class="text">Билеты</div>
          <div class="arrow">
            <img src="../public/arrowdown-outline.svg" />
          </div>
        </div>
        <ul class="dropdown">
          <li class="dropdown__item">
            <a class="dropdown__link" href="#">Входные билеты</a>
          </li>
          <li class="dropdown__item">
            <a class="dropdown__link dropdown__link_active" href="#">События</a>
          </li>
        </ul>
      </div>
      <div class="list-item">
        <div class="element">
          <div class="icon">
            <img src="../public/rouble-return.svg" />
          </div>
          <div class="text">Возвраты</div>
          <div class="returns">+12</div>
        </div>
      </div>
      <div
        @click="toggle_dropdown('reports')"
        class="list-item"
        :class="[is_dropdown_opened('reports') ? 'list-item_active' : '']"
      >
        <div class="element">
          <div class="icon">
            <img src="../public/chart-outline.svg" />
          </div>
          <div class="text">Отчёты</div>
          <div class="arrow">
            <img src="../public/arrowdown-outline.svg" />
          </div>
        </div>
        <ul class="dropdown">
          <li class="dropdown__item">
            <a class="dropdown__link" href="#">Отчеты о продажах</a>
          </li>
          <li class="dropdown__item">
            <a class="dropdown__link" href="#">Закрывающие отчеты</a>
          </li>
          <li class="dropdown__item">
            <a class="dropdown__link" href="#">Корешки билетов</a>
          </li>
        </ul>
      </div>
      <div class="list-item">
        <div class="element">
          <div class="icon">
            <img src="../public/addperson-outline.svg" />
          </div>
          <div class="text">Посетители</div>
        </div>
      </div>
    </div>
    <div class="contacts">
      <div class="element_contacts">
        <div class="icon-mini">
          <img class="icon-mini__element" src="../public/mail-outline.svg" />
        </div>
        <div class="text_sign">supportmusrum@vmuzey.com</div>
      </div>
      <div class="element_contacts">
        <div class="icon-mini">
          <img class="icon-mini__element" src="../public/phone-outline.svg" />
        </div>
        <div class="text_sign">+7 (812) 655-75-94</div>
      </div>
    </div>
    <div class="buttons">
      <button class="button">
        <img src="../public/book-outline.svg" />
      </button>
      <button class="button">
        <img src="../public/question-outline.svg" />
      </button>
      <button class="button">
        <img src="../public/document-outline.svg" />
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      active_dropdowns: new Set(),
    };
  },
  methods: {
    toggle_dropdown(dropdown_name) {
      if (this.is_dropdown_opened(dropdown_name)) {
        this.active_dropdowns.delete(dropdown_name);
      } else {
        this.active_dropdowns.add(dropdown_name);
      }
    },
    is_dropdown_opened(dropdown_name) {
      return this.active_dropdowns.has(dropdown_name);
    },
  },
};
</script>

<style>
.sidebar {
  width: 250px;
  background-color: #2e1aae;
  height: 100%;
  display: flex;
  flex-direction: column;
  position: fixed;
  top: 0;
}
.menu {
  width: 100%;
  display: flex;
  align-items: space-between;
  flex-direction: column;
  gap: 15px;
  padding: 0 10px 25px 10px;
  box-sizing: border-box;
  margin-bottom: auto;
  overflow-y: auto;
}
.logo {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  min-height: 70px;
}
.list-item {
  width: 100%;
  box-sizing: border-box;
}
.icon {
  width: 24px;
  height: 24px;
  margin-right: 11px;
  display: flex;
}

.list-item_active .arrow {
  transform: rotate(180deg);
}
.element {
  display: flex;
  align-items: center;
  color: #ffffff;
  font-weight: 700;
  font-size: 15px;
  padding: 10px 15px;
  justify-content: space-between;
  border-radius: 10px;
  transition: 0.25s ease;
  cursor: pointer;
}
.element:hover {
  background-color: #6a56e6;
}
.element_contacts {
  display: flex;
  align-items: center;
  padding: 8px 15px 8px 25px;
}
.text {
  font-size: 15px;
  margin-right: auto;
  margin-top: 1px;
}

.list-item .dropdown {
  display: none;
}
.list-item_active .dropdown {
  display: flex;
  flex-direction: column;
  gap: 6px;
  list-style-type: none;
  margin: 0;
  padding: 0 0 0 50px;
}
.returns {
  color: #9f9fb2;
}
.dropdown__link {
  font-weight: 400;
  color: #9f9fb2;
  font-size: 14px;
  text-decoration: none;
}
.dropdown__link_active {
  color: #ffffff;
}
.text_sign {
  color: #ffffff;
  font-size: 13px;
}
.contacts {
  margin-top: auto;
}
.icon-mini {
  margin-right: 8px;
  display: flex;
}
.icon-mini__element {
  width: 20px;
  height: 20px;
}
.buttons {
  display: flex;
  padding: 29px;
}
.button {
  width: 36px;
  height: 36px;
  background-color: #6a56e6;
  border-radius: 10px;
  border: none;
  margin-right: 10px;
  display: flex;
  align-items: center;
  padding: 0px;
  justify-content: center;
}
</style>
