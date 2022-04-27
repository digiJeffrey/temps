// https://www.npmjs.com/package/@nuxtjs/svg // have to manually install raw
loader
<template>
  <section class="floor-number">
    <div class="floors">
      <div class="floors-list">
        <div class="floor-carrier" v-for="num in floor" :key="num">
          <div
            v-if="num < 9"
            v-html="require(`../assets/nums/${num + 1}.svg?raw`)"
            class="floor"
          />
          <div v-else class="floor double-digits">
            <div
              v-html="require(`../assets/nums/${String(num + 1)[0]}.svg?raw`)"
            />
            <div
              v-html="require(`../assets/nums/${String(num + 1)[1]}.svg?raw`)"
            />
          </div>
        </div>
      </div>
    </div>

    <div class="sign">
      <p>/F</p>
    </div>
  </section>
</template>

<script>
export default {
  props: ['floor', 'recentFloor'],
  data() {
    return {
      // num,
      name: '2',
    }
  },
  watch: {
    recentFloor: function (val) {
      const gsap = this.$gsap
      gsap.to('.floors-list', {
        duration: 1,
        ease: 'circ.out',
        bottom: 0 - 127 * (val - 1),
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.floor-number {
  width: 450px;
  border: 1px solid blue;
  position: absolute;
  z-index: 5;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  .floors {
    border: 1px solid red;
    display: flex;
    position: relative;
    overflow: hidden;

    /* temp for test */
    width: 96px;
    height: 127px;
  }
}

.floors-list {
  position: absolute;
  bottom: 0;
}

.floor {
  padding: 18px 0;
  svg {
    color: white;
  }
}

.double-digits {
  display: flex;
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
