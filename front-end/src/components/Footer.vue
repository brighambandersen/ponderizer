<template>
  <div class="navbar-footer" id="footer">
    <p class="flex-child">Ponderizer</p>
    <a class="flex-child" href="https://github.com/brighambandersen/ponderizer">
      See Source Code
    </a>
  </div>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style scoped>
#footer {
  display: flex;
  align-items: center;
  text-align: center;
}

a {
  color: rgb(187, 187, 187);
}

i {
  font-size: small;
}
</style>
