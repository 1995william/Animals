<template>
<h1>{{ title }}</h1>
</template>

<script>
export default {
    name: "GlobalTitle",

    props: {
        title: {
            require: true,
            type: String,
        },
    },
}
</script>

<style lang="scss" scoped>
h1 {
  width: 100%;
  min-height: 50px;

  font-family: "Sail", cursive;
  font-size: 80px;
  color: #2dc653;

  display: flex;
  align-items: center;
  justify-content: center;
}

</style>