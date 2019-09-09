# 进阶写法展示

## 插入 emoji

 :point_down: 

- :fork_and_knife:Fork 这个项目并clone到本地
- :twisted_rightwards_arrows:新建一个分支: `git checkout -b new-branch`
- :wrench:增加新特性或者解决一些bug
- :memo:提交你的改变: `git commit -am 'Add some feature'`
- :rocket:推送你的分支: `git push origin new-branch`
- :tada:提交Pull Request

## 插入 vuep

?> 这里演示的是`Vue`单文件组件的三部分内容都有的情况，自定义主题色，注意下方直接演示了Vue组件的效果

<vuep template="#custom-variables"></vuep>

<script v-pre type="text/x-template" id="custom-variables">
<style>
  /* global custom-variables */
  /* :root {
    --r: 51;
    --g: 51;
    --b: 51;
  } */
  main {
    width: 100%;
    padding: 60px 29px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  label {
    display: flex;
    align-items: center;
  }
  input {
    padding: 0;
    width: 29px;
    height: 29px;
  }
  div.variables-block {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: 29px;
  }
  /* 局部 custom-variables */
  div.variables-block > div {
    --r: 51;
    --g: 51;
    --b: 51;
  }
  div.variables-block > div::after {
    content: "";
    display: inline-block;
    width: 52px;
    height: 52px;
    background: rgb(var(--r), var(--g), var(--b));
  }
</style>
<template>
  <main>
    <label for="color">
      请选择主题色：
      <input
        type="color"
        v-model="value"
        id="color"
      />
    </label>
    <div class="variables-block">
      <div
        v-for="(ele, idx) in colorList"
        :ref="'variable' + idx">
      </div>
    </div>
  </main>
</template>
<script>
  const Color = require('./libs/color.js');
  const INITIAL_COLOR = '#b4a078';
  export default {
    data() {
      return {
        value: INITIAL_COLOR,
      }
    },
    computed: {
      colorList() {
        const mainColor = this.value.length === 7 && this.value || INITIAL_COLOR;
        return this.getColorList(mainColor);
      }
    },
    methods: {
      getColorList(val) {
        const color = Color(val);
        return Array.from({length: 10}).map((v, i) => {
          let rgb = color.mix(Color('white'), i / 10);
          this.$nextTick(() => {
            const style = this.$refs[`variable${i}`][0].style;
            style.setProperty('--r', rgb.red());
            style.setProperty('--g', rgb.green());
            style.setProperty('--b', rgb.blue());
          })
        });
      }
    }
  }
</script>
</script>

## 插入 iframe

<iframe
  width="100%"
  height="800px"
  frameborder="0"
  src="https://www.baidu.com">
</iframe>