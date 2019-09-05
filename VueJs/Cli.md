> https://cli.vuejs.org/


#### install Vue CLI 3
```sh
npm install -g @vue/cli
npm install -g @vue/cli-service-global
```

#### Create Project
```sh
vue create my-project
```

#### Show user interface Project
```sh
vue ui
```

#### run Project
```sh
npm run serve
```

#### Add plugin For Vue js 3
```sh
# installs and invokes vue-cli-plugin-apollo
vue add apollo
vue add router
vue add vuex
```

#### add npm plugin that not in vue add
```sh
npm install --save axios
```

#### Add Sass Loader For Use Vue Component
```javascript
<style scoped lang="scss">
footer {
	small {
		color: blue;
	}
}
</style>
```
```
npm install --save sass-loader node-sass
```

#### Use env config File in Vue Project
```
1) create .env file in main project and add variable
APP_URL = http://site.com

2) using in component Vue
<script>
export default {
	data() {
		return {
			url : process.env.APP_URL
		}
		
	}
	
}
</script>

3) use in html
{{url}}

4) we use two files for development
.env.development
.env.production
.env.test
```

#### use env in public index html
```html
<link rel="icon" href="<%= BASE_URL %>favicon.ico">
```

#### build Vue
```sh
vue build
```

#### Starter component
```javascript
<template>
  <p> {{ greeting }} World! </p>
  <OtherComponent></OtherComponent>
</template>

<script>
import OtherComponent from './OtherComponent.vue'
export default {
  components: {
    OtherComponent
  },
  data () {
    return {
      greeting: 'Hello'
    }
  }
}
</script>

<style lang="scss" scoped>
p {
  font-size 2em
  text-align center
}
</style>
```
