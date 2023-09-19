<!-- @format -->

<template>
  <DetailModal
    @modalOff="detailModalView = false"
    :oneRooms="oneRooms"
    :detailIndex="detailIndex"
    :detailModalView="detailModalView"
  />
  <NavBar />
  <div v-for="(oneRoom, i) of oneRooms" :key="i">
    <RoomItem
      @RoomIndex="detailIndex = $event"
      @modalOn="detailModalView = true"
      @reportsPlus="oneRoom.reports += 1"
      :oneRoom="oneRoom"
    />
  </div>
</template>

<script>
import oneRooms from './db/data';
import DetailModal from './components/DetailModal.vue';
import RoomItem from './components/RoomItem.vue';
import NavBar from './components/NavBar.vue';

export default {
  name: 'App',
  data() {
    return {
      detailIndex: 0,
      oneRooms: oneRooms,
      detailModalView: false,
    };
  },
  methods: {},

  components: { DetailModal: DetailModal, RoomItem: RoomItem, NavBar: NavBar },
};
</script>

<style>
body {
  margin: 0;
  text-align: center;
}
div {
  box-sizing: border-box;
}
</style>
