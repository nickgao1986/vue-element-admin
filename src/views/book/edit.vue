<template>
  <detail :is-edit="true"></detail>
</template>

<script>
import Detail from './components/Detail'
export default {
  components: {
    Detail
  },
  data() {
    return {
      isCollapse: false
    }
  },
  methods: {
  }
}
</script>
