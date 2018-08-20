<script>
import {get} from './util'
import qcloud from 'wafer2-client-sdk'
import config from './config'
export default {
  async created () {
    // 

    // 设置登录地址
    console.log('config.loginUrl: ', config.loginUrl)
    console.log('qcloud: ', qcloud)
    qcloud.setLoginUrl(config.loginUrl);
    qcloud.login({
        success: function (userInfo) {
            console.log('登录成功', userInfo);
        },
        fail: function (err) {
            console.log('登录失败', err);
        }
    });

    // const res = await get('/weapp/demo')
    // console.log('res - util-1: ', res)
    // 调用API从本地缓存中获取数据
    // wx.request({
    //   url: config.host + '/weapp/demo', //仅为示例，并非真实的接口地址      04:51
    //   success: function(res) {
    //     console.log('res: ', res);
    //   }
    // });

    // console.log('小程序启动了！')

    // const logs = wx.getStorageSync('logs') || []
    // logs.unshift(Date.now())
    // wx.setStorageSync('logs', logs)

    // console.log('app created and cache logs by setStorageSync')
  }
}
</script>

<style>
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 200rpx 0;
  box-sizing: border-box;
}
/* this rule will be remove */
* {
  transition: width 2s;
  -moz-transition: width 2s;
  -webkit-transition: width 2s;
  -o-transition: width 2s;
}
</style>
