<template>
  <div>
    <p>index page</p>
    <nuxt-link to="/pageTwo">page 2 </nuxt-link>
    <nuxt-link to="/param">entry</nuxt-link>
    <div>
      <nuxt-link to="/Floor">floor</nuxt-link>
      <nuxt-link to="/clouds">clouds</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>
