<template>
  <div class="footer">
    <p>Copywright Jarosław Niemiec & Norbert Pedyk</p>
    <div class="links-container">
      <router-link to="/">Home</router-link>
      <div class="divider"></div>
      <router-link to="about">About</router-link>
    </div>
  </div>
</template>

<style scoped lang="less">
.links-container {
  display: flex;
  flex-direction: row;
  .divider {
    width: 0.5px;
    height: 1.1rem;
    background-color: rgb(116, 116, 116);
  }
  a {
    margin-left: 0.5rem;
    margin-right: 0.5rem;
  }
}
.footer {
  padding: 3rem;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;

  font-size: 0.875rem;
  font-weight: 300;
  opacity: 0.7;

  a,
  a:visited,
  a:active,
  a:link,
  a:hover {
    text-decoration: underline;
    color: inherit;
  }
}
</style>