<template>
  <div class="list">
    <!-- <img src="../assets/1.svg" alt="" /> -->
    <number></number>
    <ul>
      <li v-for="num in 10" :key="num">
        <div class="line"></div>
        <div class="floor">{{ num }}/F</div>
      </li>
    </ul>
  </div>
</template>

<script>
import number from '~/components/number.vue'
export default {
  components: { number },
}
</script>

<style lang="scss" scoped>
.list {
  background-color: skyblue;
  height: 800px;
  display: flex;
  justify-content: space-around;
}

img {
  transform: scale(0.5);
}

ul {
  list-style: none;
  float: right;
  margin-right: 300px;
  margin-top: 300px;
  direction: rtl;
}

li {
  height: 12px;
  position: relative;
  /* border: 1px solid red; */
  display: flex;
  align-items: center;
  padding-left: 5px;
}

.line {
  width: 12px;
  border: 1px solid #21406a;
  transition: 0.5s;
}
.floor {
  padding: 5px 12px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  position: absolute;
  right: 100%;
  direction: ltr;

  transform: scale(0);
  transition: 0.5s;

  background: #ffffff;
  border-radius: 30px;

  font-style: normal;
  font-weight: 400;
  font-size: 15px;
  line-height: 16px;

  letter-spacing: 0.04em;
  text-transform: uppercase;

  color: #21406a;
}

li:hover .line {
  width: 40px;
}

li:hover .floor {
  transform: scale(1);
}
</style>
