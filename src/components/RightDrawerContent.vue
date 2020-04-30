<template>
  <div class="q-pa-md">
    <q-btn
      @click="$emit('hideCart')"
      size="sm"
      class="float-right"
      flat
      icon="close"
      label="close"
    />
    <div class="q-mt-xl">
      <span class="text-weight-medium q-mt-xl"> CARRITO DE COMPRAS: </span>
      <q-separator class="q-mb-md q-mt-md" />
      <p class="text-center">Tu carrito está vacio</p>
      <q-btn
        class="full-width"
        outline
        style="color: #ff6666;"
        label="Continue shopping"
      />
    </div>
  </div>
</template>

<script>
export default {};
</script>
