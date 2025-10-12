<template>
  <div class="super-page">
    <div class="title">События</div>
    <div class="choose__page">
      <div class="choose__page_inactive">Входные билеты</div>
      <div class="choose__page_active">События</div>
    </div>
    <ListControls />
    <div class="events-list">
      <EventCard v-for="event of events" :key="event.id" />
    </div>
    <button class="new-event">Создать событие</button>
  </div>
</template>

<script>
import ListControls from "../components/ListControls.vue";
import EventCard from "../components/EventCard.vue";
export default {
  components: {
    ListControls,
    EventCard,
  },
  data() {
    return {
      events: [{ id: 0 }, { id: 1 }, { id: 2 }, { id: 3 }],
    };
  },
};
</script>

<style>
.events-list {
  display: flex;
  margin-top: 15px;
  flex-wrap: wrap;
  margin-right: 20px;
}
.super-page {
  padding: 30px 15px;
}
.choose__page {
  display: flex;
  width: 223px;
  justify-content: space-between;
  margin-bottom: 30px;
  font-size: 16px;
  font-weight: 700;
  margin-left: 20px;
}
.choose__page_active {
  color: #101014;
}
.choose__page_inactive {
  color: #cdcdd1;
}
.title {
  margin-bottom: 25px;
  font-weight: 700;
  font-size: 32px;
  color: #131330;
  margin-left: 20px;
}
.new-event {
  position: fixed;
  bottom: 60px;
  left: calc(50% - 130px + 125px);
  border: none;
  border-radius: 16px;
  background-color: #1212b2;
  padding: 18px;
  color: #ffffff;
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  width: 260px;
  cursor: pointer;
}
</style>
