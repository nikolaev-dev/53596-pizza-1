<template>
  <main class="content">
    <form action="#" method="post">
      <div class="content__wrapper">
        <h1 class="title title--big">Конструктор пиццы</h1>

        <BuilderDoughSelector :dough="dough" />
        <BuilderSizeSelector :sizes="sizes" />
        <BuilderIngredientsSelector
          :ingredients="ingredients"
          :sauces="sauces"
        />
        <BuilderPizzaView />
      </div>
    </form>
  </main>
</template>

<script>
import BuilderDoughSelector from "./BuilderDoughSelector";
import BuilderIngredientsSelector from "./BuilderIngredientsSelector";
import BuilderPizzaView from "./BuilderPizzaView";
import BuilderSizeSelector from "./BuilderSizeSelector";

export default {
  name: "Builder",
  props: ["dough", "ingredients", "sauces", "sizes"],
  components: {
    BuilderDoughSelector,
    BuilderIngredientsSelector,
    BuilderPizzaView,
    BuilderSizeSelector,
  },
};
</script>

<style scoped></style>
