<template>
  <div @click="clickHandle">

    <div class="userinfo" @click="bindViewTap">
      <img class="userinfo-avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl" background-size="cover" />
      <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />

      <div class="userinfo-nickname">
        <card :text="userInfo.nickName"></card>
      </div>
    </div>

    <div class="usermotto">
      <div class="user-motto">
        <card :text="motto"></card>
      </div>
    </div>

    <form class="form-container">
      <input type="text" class="form-control" :value="motto" placeholder="v-model" />
      <input type="text" class="form-control" v-model="motto" placeholder="v-model" />
      <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />
    </form>

    <a href="/pages/counter/main" class="counter">去往Vuex示例页面</a>

    <div class="all">
        <div class="left">
        </div>
        <div class="right">
        </div>
    </div>
    <van-button type="default">默认按钮</van-button>
    <van-button type="primary">主要按钮</van-button>
    <van-button type="info">信息按钮</van-button>
    <van-button type="warning">警告按钮</van-button>
    <van-button type="danger">危险按钮</van-button>
    <van-button plain type="primary">朴素按钮</van-button>
    <van-button plain type="danger">朴素按钮</van-button>
  <van-search :value="ccc" placeholder="请输入搜索关键词" />
<van-button plain hairline type="primary">细边框按钮</van-button>
<van-button plain hairline type="danger">细边框按钮</van-button>
<van-button disabled type="primary">禁用状态</van-button>
<van-button disabled type="danger">禁用状态</van-button>
<van-button loading type="primary" />
<van-button loading type="danger" loading-text="加载中..." />
<van-button square type="primary">方形按钮</van-button>
<van-button round type="danger">圆形按钮</van-button>
<van-button size="large">大号按钮</van-button>
<van-button size="normal">普通按钮</van-button>
<van-button size="small">小型按钮</van-button>
<van-button size="mini">迷你按钮</van-button>
<!-- <van-icon name="close" /> -->
<van-icon name="like" info="9" />
<!-- <van-icon name="chat" info="99+" /> -->
<van-row>
  <van-col span="8">span: 8</van-col>
  <van-col span="8">span: 8</van-col>
  <van-col span="8">span: 8</van-col>
</van-row>

<van-row>
  <van-col span="4">span: 4</van-col>
  <van-col span="10" offset="4">offset: 4, span: 10</van-col>
</van-row>

<van-row>
  <van-col offset="12" span="12">offset: 12, span: 12</van-col>
</van-row>
<van-row gutter="20">
  <van-col span="8">span: 8</van-col>
  <van-col span="8">span: 8</van-col>
  <van-col span="8">span: 8</van-col>
</van-row>

<van-transition show="show" custom-class="block">
  内容
</van-transition>
<van-cell-group>
  <van-cell title="单元格" value="内容" />
  <van-cell title="单元格" value="内容" label="描述信息cccccccsdasdasdsd" border="false" />
</van-cell-group>
<van-cell title="单元格" value="内容" size="large" />
<van-cell title="单元格" value="内容" size="large" label="描述信息" />
<van-cell title="单元格" icon="like-o" />
<van-cell title="单元格" is-link />
<van-cell title="单元格" is-link value="内容" />
<van-cell title="单元格" is-link value="内容" arrow-direction="right" />
<van-cell
  is-link
  title="单元格"
  link-type="navigateTo"
  url="../logs/main"
/>
<van-cell-group title="分组1">
  <van-cell title="单元格" value="内容1" />
</van-cell-group>
<van-cell-group title="分组2">
  <van-cell title="单元格" value="内容2" />
</van-cell-group>

<van-cell value="内容" icon="shop-o" is-link>
  <view slot="title">
    <view class="van-cell-text">单元格</view>
    <van-tag type="danger">标签</van-tag>
  </view>
</van-cell>
<van-cell title="单元格" is-link required="true">
  <van-icon slot="right-icon" name="search" class="custom-icon" />
</van-cell>
<!-- <van-popup show="{ show }" bind:close="onClose">内容</van-popup> -->
<van-popup :show="show" @click="onClose" position="bottom"
  overlay="true" duration=1000 close-on-click-overlay="true">
  <van-datetime-picker
    type="date"
    :value="currentDate"
    :min-date="minDate"
    :max-date="maxDate"
    @input="onInput"
  />
</van-popup>
<!-- <van-transition show="show" custom-class="block">
  内容
</van-transition> -->
<van-transition
  show="false"
  name="fade-up"
  duration="enter: 3000, leave: 6000"
  enter-class="van-enter-class"
  enter-active-class="van-enter-active-class"
  leave-active-class="van-leave-active-class"
  leave-to-class="van-leave-to-class"
>
内容
</van-transition>
<van-checkbox :value="checked" @change="onChange">复选框</van-checkbox>
<van-checkbox
  disabled
  :value="checked"
  @change="onChange"
>
  复选框
</van-checkbox>
<van-checkbox
 :value="checked"
 checked-color="#07c160"
 @change="onChange"
>
 复选框
</van-checkbox>
<van-checkbox use-icon-slot :value="checked" @change="onChange">
  自定义图标
  <image
    slot="icon"
    src="checked ? icon.active : icon.normal"
  />
</van-checkbox>
<van-checkbox-group :value="checked" @change="onChange" max="2">
  <van-checkbox
    :wx:for="list"
    :wx:key="index"
    :name="item"
  >
    复选框 {{ item }}
  </van-checkbox>
</van-checkbox-group>
<van-checkbox-group value="checked" @change="onChange">
  <van-cell-group >
    <van-cell
      :wx:for="list"
      :wx:key="index"
      title="复选框item"
      value-class="value-class"
      clickable
      data-index="index"
      @click="toggle"
    >
      <van-checkbox catch:tap="noop" class="checkboxes-{index}" :name="item" />
    </van-cell>
  </van-cell-group>
</van-checkbox-group>
  <van-datetime-picker
    type="date"
    :value="currentDate"
    :min-date="minDate"
    :max-date="maxDate"
    @input="onInput"
  />
  <van-datetime-picker
  type="date"
  :value="currentDate"
  :min-date="minDate"
  :formatter="formatter"
  @input="onInput"
/>
<van-datetime-picker
  type="year-month"
  :value="currentDate"
  :min-date="minDate"
  @input="onInput"
/>
<van-datetime-picker
  type="time"
  :value="currentDate"
  :min-hour="minHour"
  :max-hour="maxHour"
  @input="onInput"
/>
<van-cell-group>
  <van-field
    :value="value"
    placeholder="请输入用户名"
    clearable
    :border="false"
    @change="onChange"
  />
</van-cell-group>
<van-cell-group>
  <van-field
    :value="username"
    required
    clearable
    label="用户名"
    icon="question-o"
    placeholder="请输入用户名"
    @click-icon="onClickIcon"
  />

  <van-field
    :value="password"
    type="password"
    label="密码"
    placeholder="请输入密码"
    required
    border="true"
  />
  <van-cell-group>
    <van-field
      value="开发人员"
      label="用户名"
      left-icon="contact"
      disabled
      border="false"
    />
  </van-cell-group>
</van-cell-group>
<van-cell-group>
  <van-field
    :value="username"
    label="用户名"
    placeholder="请输入用户名"
    error
  />
  <van-field
    :value="phone"
    label="手机号"
    placeholder="请输入手机号"
    error-message="手机号格式错误"
    border="false"
  />
</van-cell-group>
<van-cell-group>
  <van-field
    :value="message"
    label="留言"
    type="textarea"
    placeholder="请输入留言"
    autosize
    border="false"
  />
</van-cell-group>
<van-cell-group>
  <van-field
    :value="sms"
    center
    clearable
    label="短信验证码"
    placeholder="请输入短信验证码"
    border="false"
    use-button-slot
  >
    <van-button slot="button" size="small" type="primary">发送验证码</van-button>
  </van-field>
</van-cell-group>
<!-- <van-picker :columns="columns" @change="onChange" /> -->
<van-radio-group :value="checked" @change="onChange" >
  <van-radio name="1" disabled>单选框 1</van-radio>
  <van-radio name="2">单选框 2</van-radio>
</van-radio-group>
<van-radio-group :value="radio" @change="onChange" >
  <van-cell-group>
    <van-cell
      title="单选框 1"
      value-class="value-class"
      clickable
      data-name="1"
      @click="onClick"
    >
      <van-radio name="1" />
    </van-cell>
    <van-cell
      title="单选框 2"
      value-class="value-class"
      clickable
      data-name="2"
      @click="onClick"
    >
      <van-radio name="2" />
    </van-cell>
  </van-cell-group>
</van-radio-group>
<!-- <van-rate :value="value" @change="onChange" /> -->
<van-rate
 :value="num"
 icon="like"
 void-icon="like-o"
 @change="onChange"
/>
<van-search :value="value" placeholder="请输入搜索关键词" />
<van-search
  :value="qqq"
  placeholder="请输入搜索关键词"
  show-action
  @search="onSearch"
  @cancel="onCancel"
/>
<van-search
  :value="ddd"
  placeholder="请输入搜索关键词"
  use-action-slot
  @search="onSearch"
  @focus="onFocus"
>
<view slot="action" @tap="onSearch">搜索</view>
</van-search>
<!-- <van-slider :value="linenum" @change="onChange" />
<p></p>
<van-slider value="50" min="10" max="90" /> -->
<van-slider
  :value="currentValue"
  use-button-slot
  @change="onChange"
>
</van-slider>
<van-stepper :value="1" @change="onChange" />
</div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      minHour: 0,
      maxHour: 23,
      radio: '1',
      num: 3,
      qqq: '',
      ddd: '',
      ccc: '',
      currentValue: 50,
      linenum: 50,
      minDate: new Date().getTime(),
      maxDate: new Date(2019, 10, 1).getTime(),
      currentDate: new Date().getTime(),
      // currentDate: '12:00',
      formatter (type, value) {
        if (type === 'year') {
          return `${value}年`
        } else if (type === 'month') {
          return `${value}月`
        }
        return value
      },
      list: ['a', 'b', 'c'],
      show: false,
      checked: false,
      motto: 'Hello miniprograme',
      icon: {
        normal: '//img.yzcdn.cn/icon-normal.png',
        active: '//img.yzcdn.cn/icon-active.png'
      },
      userInfo: {
        nickName: 'mpvue',
        avatarUrl: 'http://mpvue.com/assets/logo.png'
      }
    }
  },

  components: {
    card
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
      console.log('clickHandle:', ev)
      // throw {message: 'custom test'}
    },
    onClose (event) {
      console.log(event.mp.detail)
      console.log('aaa')
      this.show = false
    },
    onInput (event) {
      this.currentDate = event.mp.detail
    },
    onChange (event) {
      // console.log(event.detail)
      wx.showToast({
        icon: 'none',
        title: `当前值：${event.mp.detail}`
      })
      this.currentValue = event.mp.detail.value
      console.log(this.currentValue)
      // this.linenum = event.mp.detail
      this.checked = event.mp.detail
      console.log(event.mp.detail)
      this.num = event.mp.detail
      console.log(this.value)
      // const { picker, value, index } = event.mp.detail
      // console.log(this.Toast)
      // Toast(`当前值：${value}, 当前索引：${index}`)
    },
    noop () {

    },
    onClick (event) {
      const { name } = event.mp.currentTarget.dataset
      this.radio = name
    },
    onSearch (event) {
      this.qqq = event.mp.detail
      this.ddd = event.mp.detail
      console.log(this.qqq)
      console.log(this.ddd)
    },
    onCancel () {
      console.log('清空......')
    },
    onFocus () {
      this.show = true
      console.log('onfocus.....')
    }
  },

  created () {
    // let app = getApp()
  },
  toggle (event) {
    const { index } = event.mp.currentTarget.dataset
    // console.log(this.$mp.page)
    // console.log(this.$root.$mp.page)
    // console.log(this.$mp.page.selectComponent('sdsad'))
    // console.log(event)
    const checkbox = this.$mp.page.selectComponent(`.checkboxes-${index}`)
    // console.log(checkbox)
    checkbox.toggle()
  }

}
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}
.value-class {
  flex: none !important;
}
.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all{
  width:7.5rem;
  height:1rem;
  background-color:blue;
}
.all:after{
  display:block;
  content:'';
  clear:both;
}
.left{
  float:left;
  width:3rem;
  height:1rem;
  background-color:red;
}

.right{
  float:left;
  width:4.5rem;
  height:1rem;
  background-color:green;
}
.van-enter-active-class,
.van-leave-active-class {
  transition-property: background-color, transform;
}

.van-enter-class,
.van-leave-to-class {
  background-color: red;
  transform: rotate(-360deg) translate3d(-100%, -100%, 0);
}
.value-class {
  flex: none !important;
}
</style>
