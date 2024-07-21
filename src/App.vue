<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import IconContainer from './components/IconContainer.vue';
</script>

<template>
  <header>
    <div class="">
      <nav>
        <!-- <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink> -->
      </nav>
    </div>
  </header>
  <section class="hero is-primary">
    <div class="container hero-body">
      <p class="title">Dante's Marking System</p>
      <p class="subtitle">
      </p>
    </div>
  </section>
  <section>
    <div class="container">
      <div class="columns">
        <div class="column">
          <IconContainer></IconContainer>
        </div>
        <!-- <div class="column">
          <div class="field has-addons">
            <div class="control is-expanded">
              <input class="input is-large" type="text" placeholder="Competitive, trained, special, event, etc...">
            </div>
            <div class="control">
              <button class="button is-large is-primary">
                + Add
              </button>
            </div>
          </div>
        </div> -->
      </div>

    </div>
  </section>

  <!-- <RouterView /> -->


</template>

<style scoped></style>
