<template>
  <div class="app">
    <div class="container main-content">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss">
  $purple: #5e2e91;
  $green: #8cc63e;

  $primary: $purple;
  $link: $purple;
  $info: $green;

  @import "~bulma/bulma";

  .main-content {
    padding-top: 20px;
  }
</style>
