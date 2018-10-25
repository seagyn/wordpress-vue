<template>
  <div class="app">
    <nav class="navbar is-info" role="navigation" aria-label="main navigation">
      <div class="container">
        <a class="navbar-item" href="https://2018.johannesburg.wordcamp.org/">
          <img src="./assets/wordcamp-logo.png" class="navbar-logo">
        </a>

        <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>

        <div class="navbar-menu">
          <div class="navbar-start">
            <router-link class="navbar-item" to="/">Home</router-link>

            <div class="navbar-item has-dropdown is-hoverable">
              <a class="navbar-link">
                Info
              </a>

              <div class="navbar-dropdown">
                <router-link class="navbar-item" to="/sponsors">Sponsors</router-link>

                <router-link class="navbar-item" to="/speakers">Speakers</router-link>

                <router-link class="navbar-item" to="/code-of-conduct">Code of Conduct</router-link>
              </div>
            </div>

            <router-link class="navbar-item" to="/schedule">Schedule</router-link>

            <router-link class="navbar-item" to="/contact">Contact</router-link>
          </div>

          <div class="navbar-end">
            <div class="navbar-item">
              <div class="buttons">
                <router-link class="button is-primary" to="/buy-tickets">Buy Tickets</router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
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
