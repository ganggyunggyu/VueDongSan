<!-- @format -->
<template>
  <div class="modal-black-bg" v-if="detailModalView === true">
    <div class="modal-white-bg">
      <img class="modal-img" :src="oneRooms[detailIndex].image" alt="" />
      <h4>{{ oneRooms[detailIndex].title }}</h4>
      <p>{{ oneRooms[detailIndex].content }}</p>
      <p>보증금 : {{ oneRooms[detailIndex].deposit }}</p>
      <p>월세 : {{ oneRooms[detailIndex].monRent }}</p>
      <input v-model="month" />
      <p>{{ month }}</p>
      <button
        @click="
          $emit('modalOff');
          month = 0;
        "
      >
        닫기
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailModal',
  data() {
    return {
      month: 0,
      test: '',
    };
  },
  props: { oneRooms: Array, detailIndex: Number, detailModalView: Boolean },
};
</script>

<style>
.modal-black-bg {
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  position: fixed;
  padding: 20px;
}
.modal-white-bg {
  background: white;
  width: 100%;
  border-radius: 8px;
  padding: 20px;
  margin-top: 40px;
}
.modal-img {
  width: 100%;
}
</style>
