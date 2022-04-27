<template>
  <div class="floor-control">
    <number :floor="floors" :recentFloor="recentFloor"></number>

    <img
      src="../assets/floor control/AIRSIDE building 1.png"
      alt=""
      class="building"
    />

    <ul>
      <li
        v-for="num in floors"
        :key="num"
        @mouseenter="hoverFloor('enter', num)"
        @mouseleave="hoverFloor('leave')"
        @click="floorChange(num)"
      >
        <div class="line"></div>
        <div class="floor">{{ num + 1 }}/F</div>
      </li>
    </ul>
  </div>
</template>

<script>
import number from '~/components/number.vue'
export default {
  components: { number },
  layout: 'noNav',
  data() {
    return {
      floors: [...Array(44).keys()].slice().reverse(),
      recentFloor: 1,
    }
  },
  methods: {
    hoverFloor(action, num) {
      const gsap = this.$gsap
      const h = window.innerHeight
      if (action == 'enter') {
        gsap.to('.building', {
          duration: 1,
          ease: 'circ.out',
          bottom: 0 - (h / 44) * num,
        })
      } else {
        gsap.to('.building', {
          duration: 1,
          ease: 'circ.out',
          bottom: 0 - (h / 44) * (this.recentFloor - 1),
        })
      }
    },
    floorChange(num) {
      this.recentFloor = num + 1
    },
  },
}
</script>

<style lang="scss" scoped>
.floor-control {
  width: 47vw;
  height: 100vh;
  position: relative;
  background: url('../assets/floor control/Sky.png');
  background-size: cover;
  overflow: hidden;
}

.building {
  width: 100%;
  height: auto;
  position: absolute;
  bottom: 0;
  opacity: 0.5;
}

ul {
  list-style: none;
  float: right;
  direction: rtl;
  position: absolute;
  z-index: 5;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

li {
  height: 12px;
  position: relative;
  display: flex;
  align-items: center;
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
