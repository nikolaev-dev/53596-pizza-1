<template>
  <div class="content__diameter">
    <div class="sheet">
      <h2 class="title title--small sheet__title">Выберите размер</h2>

      <div class="sheet__content diameter">
        <label
          v-for="item in sizes"
          :key="item.value"
          :class="`diameter__input diameter__input--${item.value}`"
        >
          <input
            type="radio"
            name="diameter"
            value="{item.value}"
            class="visually-hidden"
          />
          <span>{{ item.name }}</span>
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BuilderSizeSelector",
  data: function () {
    return {
      sizes: [
        {
          name: "23 см",
          image: "/public/img/diameter.svg",
          multiplier: 1,
          value: "small",
        },
        {
          name: "32 см",
          image: "/public/img/diameter.svg",
          multiplier: 2,
          value: "normal",
        },
        {
          name: "45 см",
          image: "/public/img/diameter.svg",
          multiplier: 3,
          value: "big",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
