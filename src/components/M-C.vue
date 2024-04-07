


<template>
  <div class="backdrop" @click.self="closeModal">
    <div
      class="modal"
      :class="{ sale: theme === 'sale' }"
      @click.shift="closeModal"
    >
      <!-- <h2>{{ headert }}</h2>
      <p>{{ textp }}</p> -->
      <slot></slot>
      <div class="action">
        <slot name="linkss"></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["headert", "textp", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
<style>
.modal {
  widows: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(105, 33, 33, 0.5);
  width: 100%;
  height: 100%;
}
.sale {
  background: #03ccbb;
}
.action{
    background: #ff4545;
}
</style>