<template>

  <vue-scroll :ops="ops" ref="vs" id="app" class="master-container">

    <div class="page page-1">
      <div class="arrows-1"></div>
      <div class="building-1"></div>
      <div class="section-1-container">
        <div>
          <div class="big-text">Stanovanjska problematika je v Sloveniji že zdavnaj prerasla v stanovanjsko krizo.
          </div>
          <div class="small-text">V luči predloga novega stanovanjskega zakona velja pogledati, kakšna je trenutna
            situacija, kako jo naslavlja novi zakon in kaj lahko glede tega storimo sami.
          </div>
        </div>
      </div>
    </div>

    <div class="page page-2">
      <div class="section-1-container">
        <div>
          <div class="big-text">Stanovanja so čedalje težje dostopna
          </div>
          <div class="small-text">Od leta 2015 do 2018 so cene stanovanj povprečju zrasle za 22 % (približno 500 €)
            medtem ko so povprečne plače zrasle za manj kot 10 % (približno 90 €). V Ljubljani so cene poskočile celo za
            36 %.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

      <div class="section-2-container">
        <div>
          <div class="big-text">Študentje drago najemajo ali celo plačujejo turistično takso
          </div>
          <div class="small-text">V Sloveniji imamo 192.136 postelj za turiste in 9.792 postelj v javnih študentskih
            domovih. Če zaokrožimo, je na vsakih 100 turističnih namestitev le 5 študentskih.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

    </div>

    <div class="page page-3">
      <div class="section-1-container">
        <div class="room-1"></div>
      </div>

      <div class="section-2-container">
        <div>
          <div class="big-text">Stanovanjski fond je star in dotrajan
          </div>
          <div class="small-text">Evropske države za gradnjo stanovanj v povprečju namenijo 0,5 % BDP, Slovenija pa za
            stanovanjsko področje v celoti nameni le 0,04 % BDP. V proračunu za 2020-21 za gradnjo stanovanj ni
            predvidenega niti centa.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

      <div class="section-3-container">
        <div>
          <div class="big-text">Država se ne ukvarja s stanovanjsko preskrbo
          </div>
          <div class="small-text">Evropske države za gradnjo stanovanj v povprečju namenijo 0,5 % BDP, Slovenija pa za
            stanovanjsko področje v celoti nameni le 0,04 % BDP. V proračunu za 2020-21 za gradnjo stanovanj ni
            predvidenega niti centa.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

    </div>

    <div class="page page-4">
      <div class="section-1-container">
        <div class="building-2"></div>
      </div>

      <div class="section-2-container">
        <div>
          <div class="big-text">Primanjkuje javnih neprofitnih stanovanj
          </div>
          <div class="small-text">V Ljubljani se je med 1991 in 2002 delež stanovanj v javni lasti znižal iz 43 % na 6
            %. Danes je na razpisih za neprofitna stanovanja uspešnih le okoli 10 % prosilcev.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

      <div class="section-3-container">
        <div>
          <div class="big-text">Število brezdomnih se veča
          </div>
          <div class="small-text">Število brezdomnih se v Sloveniji vsako leto viša. Na pojav brezdomstva bistveno
            vpliva podivjani trg nepremičnin. Po podatkih mreže socialno-varstvenih programov je v Sloveniji okoli 6.500
            brezdomnih.
          </div>
          <div class="arrows-after-text"></div>
        </div>
      </div>

    </div>

    <div class="page page-5">

      <div class="cta-big-text">Kaj lahko storiš ?</div>

      <div class="cta-container">
        <div class="cta-items-container">
          <div class="cta-big-text-mobile">Kaj lahko storiš ?</div>
          <div class="cta-item">
            <div class="cta-item-number">1.</div>
            <div class="cta-item-text">Pozanimaj se, kakšne spremembe prinaša predlog novega stanovanjskega zakona.
              Povzetek predloga lahko prebereš tukaj.
            </div>
          </div>
          <div class="cta-item">
            <div class="cta-item-number">2.</div>
            <div class="cta-item-text">Naj odločevalci slišijo tvoj glas. Na tej povezavi lahko podaš svoje mnenje o
              novem zakonu in predloge za njegovo izboljšavo.
            </div>
          </div>
          <div class="cta-item">
            <div class="cta-item-number">3.</div>
            <div class="cta-item-text">Pridruži se iniciativi, ki si prizadeva za reševanje stanovanjske problematike.
              Seznam dejavnih iniciativ najdeš tukaj.
            </div>
          </div>

          <div class="cta-subtitle">Vpiši svoj e-naslov in ostani na tekočem z dogajanjem na stanovanjskem področju:
          </div>
          <div class="cta-input-container">
            <form class="input-form"
                  v-if="!sent"
                  id="app"
                  @submit="checkForm"
                  method="post"
            >
              <input class="cta-input" type="text" placeholder="Vpiši email..." id="email"
                     v-model="email"
                     name="email">
            </form>
            <div @click="checkForm()" class="cta-submit-button" v-if="!sent">ODDAJ</div>
            <div v-if="sent" class="sent-notice">Hvala za prijavo!</div>
          </div>

        </div>
      </div>

    </div>

    <div class="page page-6">
      <div class="end-container">
        <div style="width: 100%;">
          <div class="big-text">Več glav več ve.<br/> Deli z ostalimi!</div>
          <div class="social-container">
            <div @click="fbShare()" class="social-item social-fb"></div>
            <div @click="twitterShare()" class="social-item social-twitter"></div>
            <div @click="mailShare()" class="social-item social-mail"></div>
          </div>
        </div>
      </div>

      <div class="end-footer">Iniciativa Kje bomo pa jutri spali? v sodelovanju z Ljudje in Danes je nov dan</div>
    </div>

  </vue-scroll>


</template>

<script>

  import axios from 'axios';

  export default {
    name: 'Main',
    props: {
      msg: String
    },
    methods: {
      twitterShare: () => {
        window.open('https://twitter.com/intent/tweet?text=https://stanovanjska-kriza.je/');
      },
      fbShare: () => {
        window.open('https://www.facebook.com/sharer/sharer.php?u=#url');
      },
      mailShare: () => {
        window.open('mailto:?subject=Stanovanjska kriza&body=https://stanovanjska-kriza.je/');
      },
      checkForm: function (e) {
        this.errors = [];

        if (!this.email) {
          this.errors.push('Tvoj email ne izgleda kot email. Prosim poskusi ponovno.');
        } else if (!this.validEmail(this.email)) {
          this.errors.push('Tvoj email ne izgleda kot email. Prosim poskusi ponovno.');
        }

        if (this.errors.length) {
          alert(this.errors[0]);
          return;
        }

        axios.get(`https://api.djnd.si/sign/?email=${this.email}`)
          .then((response) => {
            this.sent = true;
          })
          .catch((error) => {
            alert('Ups, prišlo je do napake. Prosim poizkusi še enkrat.')
          });

        if (!this.errors.length) {
          return true;
        }

      },
      validEmail: function (email) {
        /*eslint no-control-regex: "error"*/
        var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return re.test(email);
      }
    },
    data() {
      return {
        ops: {
          vuescroll: {
            wheelScrollDuration: 0,
            wheelDirectionReverse: true
          },
          bar: {
            background: '#999999',
            opacity: 1
          }
        },
        email: null,
        sent: false
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

  .master-container {
    height: 100vh;
    white-space: nowrap;
    overflow-x: scroll;
    overflow-y: hidden;
    margin: 0;
    padding: 0;
  }

  /* COMMON */

  .arrows-after-text {
    width: 300px;
    height: 50px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    background-image: url("../assets/arrows.png");
    margin-top: 20px;
  }

  .page {
    position: relative;
    display: inline-block;
    width: 100%;
    height: 100vh;
    min-width: 100px;
  }

  .section-1-container {
    position: absolute;
    width: 60%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .section-2-container {
    position: absolute;
    width: 40%;
    height: 100%;
    margin-top: -150px;
    left: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .section-3-container {
    position: absolute;
    width: 40%;
    height: 100%;
    margin-top: -150px;
    left: 60%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .big-text {
    white-space: pre-wrap;
    text-align: left;
    position: relative;
    font-size: calc(1.8vw + 1.8vh);
    font-weight: 900;
  }

  .small-text {
    margin-top: 20px;
    white-space: pre-wrap;
    position: relative;
    width: 70%;
    text-align: left;
    font-size: calc(.8vw + .8vh);
    font-weight: 500;
    font-style: italic;
  }

  /* PAGE 1 */

  .page-1 {
    padding-left: 20px;
    display: inline-block;
    width: 100%;
    height: 100vh;
    position: relative;
    background-color: #EFEFF0;
  }

  .page-1 .big-text {
    white-space: pre-wrap;
    text-align: left;
    position: relative;
    font-size: calc(3vw + 3vh);
    font-weight: 900;
  }

  .page-1 .small-text {
    white-space: pre-wrap;
    position: relative;
    width: 70%;
    left: 30%;
    text-align: right;
    font-size: calc(1vw + 1vh);
    font-weight: 500;
    font-style: italic;
  }

  .building-1 {
    width: 500px;
    height: 500px;
    position: absolute;
    background-size: contain;
    background-position: bottom center;
    background-repeat: no-repeat;
    background-image: url("../assets/student.png");
    bottom: 0;
    right: 50px;
  }

  .arrows-1 {
    position: absolute;
    width: 400px;
    height: 50px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    right: 7%;
    top: 30%;
    background-image: url("../assets/arrows.png");
  }

  /* PAGE 2 */

  .page-2 .section-1-container {
    width: 40%;
  }

  .page-2 .big-text {
    white-space: pre-wrap;
    text-align: left;
    position: relative;
    font-size: calc(1.8vw + 1.8vh);
    font-weight: 900;
  }

  .page-2 .small-text {
    margin-top: 20px;
    white-space: pre-wrap;
    position: relative;
    width: 70%;
    text-align: left;
    font-size: calc(.8vw + .8vh);
    font-weight: 500;
    font-style: italic;
  }

  /* PAGE 3 */

  .page-3 .section-1-container .room-1 {
    width: 500px;
    height: 500px;
    position: absolute;
    background-size: contain;
    background-position: bottom center;
    background-repeat: no-repeat;
    background-image: url("../assets/highrent1.png");
    bottom: 0;
    left: -250px;
  }

  .page-3 .section-2-container {
    left: 20%;
    margin-top: 0;
  }

  .page-3 .section-3-container {
    margin-left: 40px;
  }


  /* PAGE 4 */

  .page-4 .section-1-container .building-2 {
    width: 500px;
    height: 500px;
    position: absolute;
    background-size: contain;
    background-position: bottom center;
    background-repeat: no-repeat;
    background-image: url("../assets/gdp1.png");
    bottom: 0;
    left: -250px;
  }

  .page-4 .section-2-container {
    left: 20%;
    margin-top: -60px;
  }

  .page-4 .section-3-container .big-text {
    margin-top: 500px;
  }

  /* PAGE 5 */

  .cta-big-text {
    white-space: pre-wrap;
    text-align: left;
    font-size: calc(3vw + 3vh);
    font-weight: 900;
    position: absolute;
    width: 20px;
    left: 150px;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10;
  }

  .cta-container {
    background-color: #c2cced;
    width: 100%;
    height: 100vh;
    border: 100px solid #EFEFF0;
    box-sizing: border-box;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .cta-items-container {
    align-items: center;
    justify-content: center;
  }

  .cta-item {
    width: 50%;
    margin: auto;
  }

  .cta-item-number {
    font-size: 80px;
    font-weight: 400;
    display: inline-block;
  }

  .cta-item-text {
    white-space: pre-wrap;
    display: inline-block;
    vertical-align: top;
    text-align: left;
    font-size: 20px;
    margin-top: 15px;
    font-style: italic;
  }

  .cta-subtitle {
    font-weight: 900;
    white-space: pre-wrap;
    text-align: left;
    font-size: 25px;
    width: 50%;
    margin: auto;
  }

  .cta-input-container {
    width: 50%;
    margin: auto;
    text-align: left;
    margin-top: 10px;
  }

  .cta-input {
    height: 39px;
    width: 94%;
    display: inline-block;
    left: 0;
    border: 0;
    padding: 0 10px;
  }

  .cta-submit-button {
    display: inline-block;
    margin-left: 5px;
    width: 45%;
    text-align: center;
    font-weight: 900;
    border: 3px solid;
    padding: 7px;
    vertical-align: middle;
    cursor: pointer;
  }

  .cta-submit-button:hover {
    opacity: 0.5;
  }

  /* PAGE 6 */

  .end-container {
    position: absolute;
    width: 100%;
    margin: auto;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .end-container .big-text {
    width: 80%;
    margin: auto;
    white-space: pre-wrap;
    text-align: center;
    font-size: 80px;
  }

  .social-container {
    margin-top: 20px;
    white-space: pre-wrap;
  }

  .social-item {
    display: inline-block;
    width: 80px;
    height: 80px;
    background-size: contain;
    background-repeat: no-repeat;
    margin-right: 5px;
    cursor: pointer;
  }

  .social-item:hover {
    opacity: 0.5;
  }

  .social-fb {
    background-image: url("../assets/fb.png");
  }

  .social-twitter {
    background-image: url("../assets/tw.png");
  }

  .social-mail {
    background-image: url("../assets/mail.png");
  }

  .end-footer {
    position: absolute;
    bottom: 10px;
    left: 0;
    width: 100%;
    text-align: center;
    white-space: pre-wrap;
  }

  .input-form {
    display: inline-block;
    width: 55%;
  }

  .sent-notice {
    text-align: center;
    font-size: 20px;
    padding: 10px 20px;
    border: 3px solid #fff;
  }

  @media screen and (max-width: 992px) {

    .page-1 .section-1-container {
      width: 45%;
    }

    .page-1 .building-1 {
      opacity: 0.5;
    }

    .page-1 .section-1-container .small-text {
      left: auto;
      width: 100%;
    }

    .small-text {
      font-size: 20px !important;
    }

    .arrows-1 {
      margin-top: -150px;
    }

    .page-2 .section-1-container {
      margin-left: -100px;
      width: 58%;
    }

    .page-2 .section-1-container .small-text {
      width: 80%;
    }

    .page-2 .section-2-container .small-text {
      width: 100%;
    }

    .page-3 .section-2-container {
      /*width: 100%;*/
    }

    .page-3 .section-2-container .small-text {
      width: 100%;
    }

    .page-3 .section-3-container {
      margin-left: 100px;
      margin-top: -120px;
      width: 50%;
    }

    .page-3 .section-3-container .small-text {
      width: 100%;
    }

    .page-4 {
      width: 150%;
    }

    .page-4 .section-2-container {
      margin-left: 60px;
      width: 30%;
    }

    .page-4 .section-2-container .small-text {
      width: 100%;
    }

    .page-4 .section-3-container {
      margin-left: 40px;
      width: 45%;
    }

    .page-4 .section-3-container .small-text {
      width: 80%;
    }

    .page-4 .section-1-container .building-2 {
      width: 350px;
      height: 350px;
    }

    .page-6 .big-text {
      font-size: 60px;
    }

    .cta-item-number {
      font-size: 20px;
    }

    .cta-item {
      margin-bottom: 5px;
      width: 50%;
    }

    .cta-item-text {
      font-size: 17px;
      margin-top: 3px;
    }

    .cta-container {
      border: 0;
    }

    .cta-big-text {
      display: none;
    }

    .cta-big-text-mobile {
      font-size: 30px;
      margin-top: -150px;
      margin-bottom: 20px;
    }

    .cta-subtitle {
      font-size: 20px;
      margin-top: 20px;
    }

    .page-6 {
      width: 60%;
      margin: 0;
      padding: 0;
      position: relative;
    }

    .page-6 .big-text {
      font-size: 30px;
    }

    .end-footer {
      width: 250px;
      left: 50%;
      margin-left: -125px;
      bottom: 100px;
    }

    .cta-input {
      margin-left: 0;
    }

  }

</style>
