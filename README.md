
<div align='center'>

# vue-sms-check-code

[![license](https://img.shields.io/badge/license-MIT-yellowgreen)](LICENSE)
[![npm](https://img.shields.io/badge/npm-vue2.6.11-blue)](https://www.npmjs.com/package/vue-sms-check-code)


[演示](https://user-images.githubusercontent.com/34472552/170011691-68b93a18-fca5-4e35-9924-ac36fb5d5972.mp4)


<div align='left'>


<h1>running</h1>

```vue

1,npm install vue-sms-check-code --save

2,import VueSmsCode from 'vue-sms-check-code'

3,vue.use(VueSmsCode)

```

```vue

<vue-sms-check-code
    title='请输入验证码' 
    :code-num='6'
    :is-error='isError'
    error-color='#D81A1A'
    @finish='getSmsCode'
/>
```

| 事件  |  说明  | 默认  |  类型
|:----: |:----: |:----: | :----: 
| title    | 组件标题   | 请输入验证码 | string
| code-num | 验证码个数 | 6   | number
| is-error | 验证码是否错误 | false | boolean
| error-color | 验证码错误时显示的错误颜色 | #D81A1A | string


| 方法          | 说明   | 默认   |  类型
|:----: |:----: |:----: | :----: 
| finish       | 验证码值 | '' | string



<h1>demo</h1>

```vue
<template>
  <div id="app">
    <vue-sms-check-code
        title='请输入验证码'
        :codeNum='6'
        :is-error='isError'
        error-color='#D81A1A'
        @finish='getSmsCode'
    />
    {{msg}}
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      isError: false, // 验证码错误
      msg: ''
    }
  },
  methods: {
    getSmsCode(val) {
      this.isError = false
      this.msg = val
      setTimeout(() => {
        this.isError = val !== '888888';
        if(val === '888888') {
          this.msg = '验证码输入成功'
        }
      }, 1000)
    }
  }
}
</script>

<style>
html, body {
  padding: 0;
  margin: 0;
}
</style>

```

</div>

</div>


<h1>源码地址，欢迎star</h1>

[github地址](git@git.zhlh6.cn:snailBody/vue-sms-check-code.git)

[gitee地址](https://gitee.com/snailBody/vue-sms-check-code.git)



