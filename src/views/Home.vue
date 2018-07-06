<template>
  <div class="home">
    <img src="../assets/logo.png">
    <dynamicLink :type="'HelloWorld'"></dynamicLink>
    <dynamicLink :type="'HelloMoon'"></dynamicLink>
    <dynamicLink :type="'HelloSun'"></dynamicLink>
    <dynamicLink :type="'HelloMar'"></dynamicLink> // Does not exist component
  </div>
</template>

<script>
// @ is an alias to /src
import dynamicLink from '@/components/DynamicLink'

export default {
  props: ['type'],
  name: 'home',
  components: {
    dynamicLink
  }
}
</script>
