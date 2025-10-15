<template>
  <div class="list_controls">
    <div class="platform__choise">
      <div class="platform__choise_various">
        <div
          @click="toggle_vm_dropdown('platforms')"
          class="platform__choise_name"
          :class="[
            is_vm_dropdown_opened('platforms') ? 'platform__choise_active' : '',
          ]"
        >
          <div class="platform__choise_text">Выбраны все площадки</div>
          <div class="list_arrow">
            <img src="../public/checkmark_16.svg" />
          </div>
        </div>
        <div class="vm_dropdown">
          <div class="vm-dropdown__link">
            <img
              class="platform__choise_img"
              src="https://api.vmuzey.com/static/museum/433975671749776/bb6edad6a24c31c3-w295-h165.JPG"
            />
            <div class="vm-dropdown__link_content">
              <div class="vm-dropdown__link_title">Ливадийский дворец</div>
              <div class="vm-dropdown__link_subtitle">Ливадия</div>
            </div>
            <div class="vm-dropdown_checkbox">
              <img
                class="dropdown_checkbox"
                src="https://organization.vmuzey.com/_nuxt/img/checked-icon.87bddce.svg"
              />
            </div>
          </div>
        </div>
      </div>
      <div class="platform__choise_status">
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
export default {
  data() {
    return {
      active_vm_dropdown: new Set(),
    };
  },
  methods: {
    toggle_vm_dropdown(vm_dropdown) {
      if (this.is_vm_dropdown_opened(vm_dropdown)) {
        this.active_vm_dropdown.delete(vm_dropdown);
      } else {
        this.active_vm_dropdown.add(vm_dropdown);
      }
    },
    is_vm_dropdown_opened(vm_dropdown) {
      return this.active_vm_dropdown.has(vm_dropdown);
    },
  },
};
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
.platform__choise_active .list_arrow {
  transform: rotate(180deg);
}
.platform__choise_various {
  display: flex;
  flex-direction: column;
  position: relative;
}
.platform__choise_name ~ .vm_dropdown {
  display: none;
}
.platform__choise_active ~ .vm_dropdown {
  display: flex;
  align-items: center;
  position: absolute;
  top: 55px;
  background-color: white;
  border: 1px solid #bebfd1;
  padding: 15px;
  border-radius: 12px;
  box-sizing: border-box;
  width: 100%;
  box-shadow: 5px 5px 15px 1px #bebfd1;
}
.vm-dropdown__link {
  display: flex;
  width: 100%;
  align-items: center;
}
.vm-dropdown__link_content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.vm-dropdown__link_title {
  font-weight: 700;
  margin-bottom: 8px;
  color: #1212b2;
}
.vm-dropdown__link_subtitle {
  color: #cdcdd1;
  margin-bottom: 0;
}
.vm-dropdown_checkbox {
  border-radius: 50%;
  width: 20px;
  height: 20px;
  background-color: #4545e5;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: auto;
}
.dropdown_checkbox {
  width: 9px;
  height: 9px;
}
.platform__choise_img {
  width: 100px;
  height: 55px;
  border-radius: 10px;
  margin-right: 15px;
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
.platform__choise_status {
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
