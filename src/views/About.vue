<template>
  <div class="about">
    <div class="view">
      <h4>
        Projekt został stworzony w ramach kursu Usługi Sieciowe prowadzonego na
        Uniwersytecie Ekonomicznym. Głównymi założeniami było stworzenie
        mechanizmu logowania z szyfrowaniem, wykorzystanie baz danych i
        sztucznej inteligencji.
      </h4>
    </div>
  </div>
</template>

<style scoped lang="less">
.about {
  padding: 3rem;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .view {
    width: 100%;
    height: 70vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    h4 {
      font-size: 1rem;
      font-weight: 400;
      max-width: 50%;

      background-color: rgba(#8a978a, 0.9);
      color: transparent;
      text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.3);
      -webkit-background-clip: text;
      -moz-background-clip: text;
      background-clip: text;
    }
  }
}
</style>