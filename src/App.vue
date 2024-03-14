<script  lang="ts">
import { defineComponent, ref, reactive } from "vue";
interface Person {
  name: string,
  age: number
}
export default defineComponent({
  name: "App",
  setup() {
    const count = ref<number | string>(0)
    const incrment = () => {
      count.value++
    }
    const user: Person = reactive({
      name: 'ReginYuan',
      age: 25
    })
    return {
      count,
      incrment,
      user
    }
  }
})
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <h1>{{ user.name }}</h1>
    <h1>{{ user.age }}</h1>
    <h1>{{ count }}</h1>
    <button @click="incrment">新增</button>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
