<template>
  <div class="content-area" >
    <div v-title='title'>
      {{title}}
    </div>
      <div class="group">
          <div class="span12 path-nav ">
              <ol>
                  <li><a href="#"><strong></strong></a></li>
              </ol>
          </div>
      </div>
      <div class="content-body" >
        <span class="font2" style="margin:100px auto;display:block;width:600px;overflow: hidden;">
          <span class="iconfont icon-success " style="font-size:80px;margin-right:30px;color:#fb642a;float:left"></span>
          <span style="display:block;margin-top:50px"><strong>{{content}}</strong>
          </span>
        </span>
      </div>
  </div>
</template>

<script type="text/javascript">
import 'common/css/lib/iconfont.css'
import 'common/css/lib/motherplate.css'
import 'common/sass/main.scss'
import 'common/sass/module/account.scss'
import vnav from 'components/include/nav'
import left from 'components/include/left'
import vfooter from 'components/include/footer'

export default {
  name: 'app',
  components: {
    vnav: vnav,
    left: left,
    vfooter: vfooter
  },
  data () {
    return {
      title: '成功页面',
      content: '',
      active: ''
    }
  },
  mounted () {
    this.content = this.$route.query.content
    this.active = this.$route.query.active
    if (this.$route.query.title) {
      document.title = this.$route.query.title
    }
    this.$bus.$emit('liActive', this.active)
  },
  methods: {
  }
}
</script>
