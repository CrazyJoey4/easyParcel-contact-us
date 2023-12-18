<script setup>
import HeaderComponent from './components/Header.vue';
import FooterComponent from './components/Footer.vue';
import HeadingBlock from './components/HeadingBlock.vue';
import MainButtons from './components/FormButtons.vue';
import LiveChatBlock from './components/LiveChatBlock.vue';
</script>

<template>
  <div>
    <HeaderComponent />

    <main>
      <div class="content">
        <div class="container">
          <div class="heading">
            <HeadingBlock />
          </div>
          <div class="mainButtons">
            <MainButtons />
          </div>
          <div class="liveChat">
            <LiveChatBlock />
          </div>
        </div>
      </div>
    </main>

    <FooterComponent />
  </div>
</template>


<style scoped>
.content {
  background-color: var(--white-soft);
  padding: 60px 45px;
  padding-bottom: 140px;

  margin-left: auto;
  margin-right: auto;
}

.container {
  max-width: 1170px;
  margin-left: auto;
  margin-right: auto;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>
