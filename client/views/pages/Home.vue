<template>
  <div>
    <p>{{ systemName }}</p>
    <p>{{ currentDate }}</p>
    <h2>这是首页</h2>
    <h4>验证成功了</h4>
  </div>
</template>

<script>
import { mapState, mapMutations, mapGetters, mapActions } from 'vuex'

export default {
  name: 'Home',
  data () {
    return {}
  },
  computed: {
    ...mapState(['sysPrefixName', 'sysSuffixName', 'currentDate']),
    ...mapGetters(['systemName'])
  },
  mounted () {
    this.realTimeUpdate({
      time: 1000
    })
    this.updateSysemName({
      sysPrefixName: '大数据',
      sysSuffixName: '研判分析平台'
    })
  },
  methods: {
    ...mapActions(['realTimeUpdate']),
    ...mapMutations(['updateSysemName'])
  }
}
</script>
