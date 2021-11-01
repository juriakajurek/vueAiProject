<template>
  <div class="home">
    <div class="view">
      <div class="description">
        <h3 class="">Zaplanuj z nami zakup bądź sprzedaż nieruchomości</h3>
        <p class="">
          Nasz innowacyjny algorytm potrafi przewidziec przyszłą cenę
          nieruchomości
        </p>
      </div>
      <div class="photo">
        <img :src="Planning" alt="" />
      </div>
    </div>
    <div class="content">
      <div class="photo">
        <img :src="HouseChart" alt="" />
      </div>
      <div class="description">
        <h3 class="">Dodawaj nieruchomości i przewiduj wahania cen</h3>
        <p class="">
          Miej wszystko na oku - wprowadź nieruchomości którymi jesteś
          zainteresowany i obserwuj zmiany ich ceny na czytelnych wykresach
        </p>
      </div>
    </div>
    <div class="content">
      <div class="description">
        <h3 class="">Wybierz odpowiedni moment na zakup</h3>
        <p class="">
          Nasz program pomoże Ci przewidzieć, kiedy cena nieruchomości będzie
          najniższa
        </p>
      </div>
      <div class="photo">
        <img :src="Scale" alt="" />
      </div>
    </div>
    <div class="content">
      <div class="photo">
        <img :src="HouseBank" alt="" />
      </div>
      <div class="description">
        <h3 class="">Maksymalizuj zysk ze sprzedaży</h3>
        <p class="">
          Znając przyszłą cenę nieruchomości spieniężysz ją w najbardziej
          odpowiednim momencie
        </p>
      </div>
    </div>
    <div class="join-now-section">
      <div class="description">
        <h3 class="">Z nami to proste</h3>
        <p class="">
          Dołącz teraz i nie daj się zaskoczyć tym, co przyniesie przyszłosć.
        </p>
      </div>
      <Button
        bigbutton="true"
        @button-click="joinNowClicked()"
        text="Dołącz teraz"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import router from "../router";

import Planning from "../assets/planning.png";
import HouseChart from "../assets/houseChart.png";
import Scale from "../assets/scale.png";
import HouseBank from "../assets/houseBank.png";

import Button from "../components/Button";

export default {
  name: "Home",
  data() {
    return {
      Planning: Planning,
      HouseChart: HouseChart,
      Scale: Scale,
      HouseBank: HouseBank,
    };
  },
  components: { Button },
  methods: {
    joinNowClicked() {
      router.push("signin");
    },
  },
};
</script>

<style lang="less" scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .view {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    .description {
      margin: 2rem;
      padding: 2rem;
      width: 25vw;
      h3 {
        font-size: 1.5rem;
        font-weight: 800;
        text-align: left;
        margin-bottom: 0.5rem;

        background-color: #8a978a;
        color: transparent;
        text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.3);
        -webkit-background-clip: text;
        -moz-background-clip: text;
        background-clip: text;
      }
      p {
        font-size: 1rem;
        font-weight: 400;
        text-align: left;
        margin-top: 0rem;

        background-color: rgba(#8a978a, 0.8);
        color: transparent;
        text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.3);
        -webkit-background-clip: text;
        -moz-background-clip: text;
        background-clip: text;
      }
    }
    .photo {
      margin: 2rem;

      img {
        width: 45vw;
        border-radius: 50%;
      }
    }
  }

  .content {
    width: 100%;
    height: 60vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    .description {
      margin: 2rem;
      padding: 2rem;
      width: 25vw;
      h3 {
        font-size: 1rem;
        font-weight: 800;
        text-align: left;
        margin-bottom: 0.5rem;

        background-color: #8a978a;
        color: transparent;
        text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.3);
        -webkit-background-clip: text;
        -moz-background-clip: text;
        background-clip: text;
      }
      p {
        font-size: 0.875rem;
        font-weight: 400;
        text-align: left;
        margin-top: 0rem;

        background-color: rgba(#8a978a, 0.8);
        color: transparent;
        text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.3);
        -webkit-background-clip: text;
        -moz-background-clip: text;
        background-clip: text;
      }
    }
    .photo {
      margin: 2rem;

      img {
        width: 30vw;
        border-radius: 0.5rem;
      }
    }
  }
  .join-now-section {
    margin-top: 3rem;
    // margin-bottom: 1rem;
    width: 80%;
    border: solid 2px #404e40;
    border-radius: 1.5rem;
    padding-bottom: 0.5rem;
    .description {
      background-color: rgba(#8a978a, 0.8);
      color: transparent;
      text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.1);
      -webkit-background-clip: text;
      -moz-background-clip: text;
      background-clip: text;

      h3 {
        margin-left: 2rem;
        margin-right: 2rem;
        margin-bottom: 0;
        margin-top: 1.2rem;

        text-align: left;
        font-size: 2rem;
        font-weight: 800;
      }
      p {
        margin-top: 0.2rem;
        margin-left: 2rem;
        margin-right: 2rem;

        text-align: left;
        font-size: 1rem;
        font-weight: 600;
      }
    }
  }
}
</style>