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
            class="visually-hidden"
            :value="item.value"
            :checked="item.value == value"
            @change="$emit('input', $event.target.value)"
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
  props: ["sizes", "value"],
};
</script>

<style scoped></style>
