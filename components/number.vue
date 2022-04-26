<template>
  <!-- 以下為數字1的svg -->
  <svg
    version="1.1"
    id="num"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    x="0px"
    y="0px"
    viewBox="0 0 41 87"
    style="enable-background: new 0 0 41 87"
    xml:space="preserve"
  >
    <style type="text/css">
      .st0 {
        fill: #ffffff;
      }
    </style>
    <path class="st0" d="M26.3,0.2h-0.9v86.5h0.9V0.2z" />
    <path class="st0" d="M22.7,0.2h-0.9v86.5h0.9V0.2z" />
    <path class="st0" d="M19.1,0.2h-0.9v86.5h0.9V0.2z" />
    <path class="st0" d="M15.5,0.2h-0.9v86.5h0.9V0.2z" />
    <path class="st0" d="M12,73.4h-0.9v13.3H12V73.4z" />
    <path class="st0" d="M8.4,73.4H7.5v13.3h0.9V73.4z" />
    <path class="st0" d="M4.8,73.4H3.9v13.3h0.9V73.4z" />
    <path class="st0" d="M1.2,73.4H0.3v13.3h0.9V73.4z" />
    <path class="st0" d="M12,0.2h-0.9v13.3H12V0.2z" />
    <path class="st0" d="M8.4,0.2H7.5v13.3h0.9V0.2z" />
    <path class="st0" d="M4.8,0.2H3.9v13.3h0.9V0.2z" />
    <path class="st0" d="M40.7,73.4h-0.9v13.3h0.9V73.4z" />
    <path class="st0" d="M37.1,73.4h-0.9v13.3h0.9V73.4z" />
    <path class="st0" d="M33.5,73.4h-0.9v13.3h0.9V73.4z" />
    <path class="st0" d="M29.9,73.4H29v13.3h0.9V73.4z" />
  </svg>
</template>

<script>
export default {
  methods: {
    animate() {
      const timeline = this.$gsap.timeline()
      timeline.to('.st0', { opacity: 0, stagger: 0.05 })
    },
  },
  mounted() {
    this.animate()
  },
}
</script>

<style scoped>
#num {
  transform: scale(0.5);
}
</style>
