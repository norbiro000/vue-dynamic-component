<template>
  <component :is="component"></component>
</template>

<script>
export default {
  props: ['type', 'msg'],
  data () {
    return {
      component: null
    }
  },
  computed: {
    loader () {
      if (!this.type) {
        return null
      }
      return () => import(`@/components/${this.type}`)
    }
  },
  mounted () {
    this.loader().then((component) => {
      this.component = () => this.loader()
    }).catch((e) => {
      this.component = () => import('@/components/HelloWorld')
    })
  }
}
</script>

<style>

</style>
