<template>
  <header class="header">
    <h1 class="header__logo">
      <img :src="logo" alt="Ubook logo" />
    </h1>
    <form class="header__form">
      <input
        type="text"
        class="header__inputSearch"
        :placeholder="placeholder"
      />
    </form>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      placeholder: "Buscar",
    };
  },
  props: {
    logo: {
      required: true,
      type: String,
    },
  },
};
</script>

<style scoped lang="scss">
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 16px;

  &__logo {
    width: 148px;
    height: 32px;
  }

  &__form {
    display: flex;
    position: relative;
    width: calc(100% - 228px);

    &::before {
      background-image: url("../assets/ic-search.svg");
      content: "";
      position: absolute;
      top: 15px;
      right: 15px;
      width: 16px;
      height: 16px;
    }
  }

  &__inputSearch {
    border: 0;
    border-radius: 4px;
    background-color: #e4e7f4;
    padding: 7px 35px 6px 8px;
    width: 100%;
    height: 32px;

    &:focus-visible {
      outline: none;
    }
  }
}
</style>
