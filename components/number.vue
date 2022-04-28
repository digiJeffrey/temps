// https://www.npmjs.com/package/@nuxtjs/svg // have to manually install raw
loader
<template>
  <section class="floor-number">
    <div class="floors-frame">
      <ul class="floors-list">
        <li class="floor-carrier" v-for="num in floor" :key="num ">
          <digit v-if="num<9" :number="num + 1"></digit>
          <div v-else class="double-digits">
            <digit :number="String(num + 1)[0]"></digit>
            <digit :number="String(num + 1)[1]"></digit>
          </div>
        </li>

      </ul>
    </div>

    <div class="sign">
      <p>/F</p>
    </div>
  </section>
</template>

<script>
import digit from './digit.vue'


export default {
  components: { digit },
  props: ['floor', 'recentFloor'],
  watch: {
    recentFloor: function (val) {
      const gsap = this.$gsap
      gsap.to('.floors-list', {
        duration: 1,
        ease: 'circ.out',
        bottom: 0 - 236 * (val - 1),
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.floor-number {
  width: 450px;
  position: absolute;
  z-index: 5;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  .floors-frame {
    display: flex;
    position: relative;
    overflow: hidden; 
    width: 247px;
    height: 236px;

    /* temp for test */
  }
}

.floor-carrier{
  width: 247px;
  height: 236px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.floors-list {
  position: absolute;
  bottom: 0;
}


.double-digits {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.sign {
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  p {
    color: white;
    font-weight: 400;
    font-size: 54px;
    line-height: 120%;
    letter-spacing: 0.02em;
  }
}
</style>
