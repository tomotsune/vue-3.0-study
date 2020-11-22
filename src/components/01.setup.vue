<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ user.id }}</p>
  </div>
</template>

<script>
export default {
  name: "01.setup",
  // 在beforeCreate前执行.
  // 第一ge
  // =setup:()=>{}
  setup(props, context) {
    // 相当于data.
    // 暴露给模板
    console.log(props.msg)
    console.log(context);
    return {
      name: 'tom',
      user: {
        id: '001',
        pwd: '123'
      }
    }
  },
  beforeCreate() {
    // console.log('beforeCreate')
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>
