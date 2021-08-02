<template>
  <div class="content__ingridients">
    <div class="sheet">
      <h2 class="title title--small sheet__title">Выберите ингридиенты</h2>

      <div class="sheet__content ingridients">
        <div class="ingridients__sauce">
          <p>Основной соус:</p>

          <label
            v-for="item in sauces"
            :key="item.value"
            class="radio ingridients__input"
          >
            <input type="radio" name="sauce" value="tomato" checked />
            <span> {{ item.name }}</span>
          </label>
        </div>

        <div class="ingridients__filling">
          <p>Начинка:</p>

          <ul class="ingridients__list">
            <li
              v-for="item in ingredients"
              :key="item.name"
              class="ingridients__item"
            >
              <span :class="`filling filling--${item.value}`">{{
                item.name
              }}</span>

              <ItemCounter />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ItemCounter from "../../common/components/ItemCounter";
export default {
  name: "BuilderIngredientsSelector",
  props: ["ingredients", "sauces"],
  components: { ItemCounter },
};
</script>

<style scoped></style>
