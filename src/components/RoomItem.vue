<!-- @format -->

<template>
  <img
    @click="
      $emit('modalOn');
      $emit('RoomIndex', oneRoom.id);
    "
    :src="oneRoom.image"
    alt=""
    class="item-img"
  />
  <h4>{{ oneRoom.title }}</h4>
  <p>{{ oneRoom.deposit }} / {{ oneRoom.monRent }}</p>
  <div>
    <button @click="$emit('reportsPlus')">신고하기</button>
    <span>신고수 {{ oneRoom.reports }}</span>
  </div>
</template>

<script>
export default {
  name: 'RoomItem',
  props: { oneRoom: Object },
};
</script>

<style>
.item-img {
  width: 100%;
  margin-top: 40px;
}
</style>
