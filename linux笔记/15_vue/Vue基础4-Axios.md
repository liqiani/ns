## 一、数据获取
Vue 原本有一个官方推荐的 ajax 插件 [vue-resource](https://github.com/pagekit/vue-resource)，但是自从 Vue 更新到 2.0 之后，官方就不再更新 vue-resource。目前主流的 Vue 项目，都选择 [axios](https://github.com/mzabriskie/axios)  来完成 ajax 请求，而大型项目都会使用 Vuex 来管理数据。

- 安装axios
    ```
    npm install --save axios
    ```

- 关于axios插件的引入
在`main.js`中引入，但是 axios 并不能`Vue.use`，只能每个需要发送请求的组件中即时引入。为了解决这个问题，是在引入 axios 之后，修改原型链。
    ```
    // main.js
    // 导入Axios插件
    import Axios from 'axios'
    // 如果在其它的组件中，是无法使用 axios 命令的。但如果将 axios 改写为 Vue 的原型属性
    Vue.prototype.$ajax = Axios;
    ```
    ```
    // 其他组件，例如App.vue
    // 新闻接口: https://www.apiopen.top/journalismApi
    export default {
    	data() {
    		return {
    			tech: null
    		}
    	},
    	created() {	// 钩子函数 mounted: el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用该钩子
    		// 获取数据
    		this.$ajax.get('https://www.apiopen.top/journalismApi')
    			.then(response => (this.tech = response.data.data.tech))
    			.catch(err => console.log('错误提示:' + err))
    	},
    }
    ```