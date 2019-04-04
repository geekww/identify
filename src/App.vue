<template>
  <div id="app">
    <identify :identifyCode.sync="identifyCode" ref="identify" @handleClickPanel="handleClickPanel"></identify>
    <p>{{identifyCode}}</p>
  </div>
</template>

<script>
import identify from './components/identify'
export default {
  name: 'app',
  components: {identify},
  data () {
    return {
      identifyCode: ''
    }
  },
  methods: {
    handleClickPanel () {
      // 刷新验证码
      this.$refs.identify.refreshCode()
    }
  },
  mounted () {
    this.handleClickPanel()
  }
}
</script>
