<template>
    <li>
        <div class="image" :style="{ backgroundImage: 'url(' + item.image_link + ')' }"></div>
        <p>{{ item.name.length > 15 ? item.name.substr(0,14) + "..." : item.name }}</p>
    </li>
</template>

<script>
export default {
    props: {
        item: {
            require: true,
            type: Object,
        },
    }
}
</script>

<style lang="scss">
li {
  width: 40%;
  height: 60%;

  background-color: #2dc653;

  border-radius: 20px;
  padding: 5px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  margin-bottom: 10px;

  .image {
    width: 100%;
    height: 90%;

    border-radius: 20px;

    background-size: cover;
    // background-position: center;
  }

  p {
    color: #fff;
    font-size: 25px;
  }
}

</style>