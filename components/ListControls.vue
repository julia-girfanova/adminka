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
      <div class="platform__status">
        <div
          class="platform__status_name"
          @click="insert_status__dropdown('status')"
          :class="[
            is_status__dropdown_opened('status')
              ? 'platform__status_active'
              : '',
          ]"
        >
          <div class="platform__choise_text">{{ status_select_text }}</div>
          <img class="status_arrow" src="../public/checkmark_16.svg" />
        </div>
        <div class="status__dropdown">
          <div
            class="status__dropdown_vm"
            v-for="status in statuses"
            @click="select_status(status.id)"
            :key="status.id"
          >
            <div class="status__dropdown_name">{{ status.name }}</div>
            <div
              class="status__dropdown_checkbox"
              :class="[
                is_dropdown_checkbox_registered(status.id)
                  ? 'status__dropdown_checkbox_active'
                  : '',
              ]"
            >
              <img
                class="dropdown_checkbox"
                src="https://organization.vmuzey.com/_nuxt/img/checked-icon.87bddce.svg"
              />
            </div>
          </div>
        </div>
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
      active_status__dropdown: new Set(),
      select_status__dropdown: new Set(),
      statuses: [
        { id: "active", name: "Активный" },
        { id: "canceled", name: "Отменен" },
        { id: "finished", name: "Завершено" },
      ],
    };
  },
  computed: {
    status_select_text() {
      if (this.select_status__dropdown.size === 0) {
        return "Выберите статус";
      } else {
        return [...this.select_status__dropdown]
          .map((id) => {
            return this.statuses.find((status) => {
              return status.id === id;
            }).name;
          })
          .join(", ");
      }
    },
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
    insert_status__dropdown(status__dropdown) {
      if (this.is_status__dropdown_opened(status__dropdown)) {
        this.active_status__dropdown.delete(status__dropdown);
      } else {
        this.active_status__dropdown.add(status__dropdown);
      }
    },
    is_status__dropdown_opened(status__dropdown) {
      return this.active_status__dropdown.has(status__dropdown);
    },
    select_status(status_name) {
      if (this.select_status__dropdown.has(status_name)) {
        this.select_status__dropdown.delete(status_name);
      } else {
        this.select_status__dropdown.add(status_name);
      }
    },

    is_dropdown_checkbox_registered(status_id) {
      return this.select_status__dropdown.has(status_id);
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
.status__dropdown_checkbox {
  border-radius: 30%;
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #73737a;
  margin-left: auto;
}
.status__dropdown_checkbox .dropdown_checkbox {
  display: none;
}
.status__dropdown_checkbox_active .dropdown_checkbox {
  display: flex;
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
.platform__status {
  display: flex;
  flex-direction: column;
  position: relative;
}
.platform__status_name {
  border: 1px solid #bebfd1;
  border-radius: 16px;
  width: 220px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.platform__status_name ~ .status__dropdown {
  display: none;
}
.platform__status_active ~ .status__dropdown {
  width: 100%;
  height: 156px;
  border: 1px solid #bebfd1;
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 55px;
  background-color: white;
  box-shadow: 5px 5px 15px 1px #bebfd1;
  box-sizing: border-box;
}
.status__dropdown_vm {
  height: 52px;
  width: 100%;
  display: flex;
  align-items: center;
  padding-left: 16px;
  padding-right: 16px;
  border-radius: 16px;
  cursor: pointer;
  box-sizing: border-box;
}
.status_arrow {
  width: 16px;
  height: 16px;
  margin-right: 18px;
}
.platform__status_active .status_arrow {
  transform: rotate(180deg);
}
.status__dropdown_vm:hover {
  background-color: #f4f4f6;
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
