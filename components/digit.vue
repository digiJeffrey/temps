<template>
  <Component
     :is="require(`../assets/nums/${number}.svg?inline`)"
     class="digit"
  />
</template>

<script>
export default {
  name: 'BaseIcon',

  // Transparent wrapper component
  // https://vuejs.org/v2/guide/components-props.html#Disabling-Attribute-Inheritance
  inheritAttrs: false,

  props:['number']
}
</script>

<style lang="scss" scoped>
 svg{
     width: 108px;
     height: 200px;
    path{
        fill: white;
     }
 }
</style>