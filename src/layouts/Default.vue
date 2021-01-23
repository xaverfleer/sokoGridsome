<template>
  <div class="layout">
    <header class="header">
      <div class="header__emotion"></div>
      <div class="header__content">
        <g-link class="header__home" to="/">
          <g-image
            alt="Logo mit Giesskanne, die den inneren Baum deines Kindes
          nährt."
            class="header__logo"
            src="~/assets/logo.png"
            title="Zur Startseite"
          />
        </g-link>
        <nav class="nav">
          <a
            class="nav__entry nav__entry--primary"
            href="./kurs.html"
            target="_blank"
            >Gratis starten</a
          >
          <a class="nav__entry nav__entry--2ndary" href="#contents">Inhalte</a>
          <a class="nav__entry nav__entry--2ndary" href="#offer">Angebot</a>
          <a class="nav__entry nav__entry--2ndary" href="#pricing">Preise</a>
          <a class="nav__entry nav__entry--2ndary" href="#about-us"
            >Über mich</a
          >
          <a class="nav__entry nav__entry--2ndary" href="#contact">Kontakt</a>
        </nav>
      </div>
    </header>
    <slot />
    <footer class="footer">
      <div id="contact">
        Kontaktiere uns unter
        <a href="mailto:kurs@so-kommunizieren.ch" rel="nofollow"
          >kurs@so-kommunizieren.ch</a
        >
        oder
        <a href="tel:+41774466505" rel="nofollow">
          +41 77 44 66 505
        </a>
      </div>
      <div class="footer__copyright">© 2021 Fleer & Fleer</div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
module.exports = {
  mounted: () => {
    // /* global XMLHttpRequest, alert, amplitude, document, localStorage, window */
    // import LogRocket from "logrocket";

    const header = document.querySelector(".header");
    const nav = document.querySelector(".nav");
    // const formElem = document.querySelector("form");

    // const hideGdpr = () =>
    //   document.querySelector(".gdpr").setAttribute("style", "display: none;");

    // function consentRequiringActions() {
    //   if (window.location.toString().indexOf("localhost") === -1) {
    //     LogRocket.init("yxvjmb/soko");
    //     amplitude.getInstance().logEvent("Page loaded");

    //     document.querySelectorAll(".cta05").forEach(function bindHandler(e) {
    //       e.addEventListener("click", function logEvent() {
    //         amplitude.getInstance().logEvent("Jetzt buchen");
    //       });
    //     });
    //   }
    // }

    // const storageGdpr = localStorage.getItem("soko-gdpr");

    // if (["accepted", "ignored"].indexOf(storageGdpr) >= 0) {
    //   hideGdpr();
    // } else {
    //   const elems = {
    //     accept: document.getElementById("gdpr__accept"),
    //     ignore: document.getElementById("gdpr__ignore"),
    //   };
    //   const handle = {
    //     accept: () => {
    //       localStorage.setItem("soko-gdpr", "accepted");
    //       hideGdpr();
    //       handle.unbind();
    //       consentRequiringActions();
    //     },
    //     ignore: () => {
    //       localStorage.setItem("soko-gdpr", "ignored");
    //       hideGdpr();
    //       handle.unbind();
    //     },
    //     unbind: () => {
    //       elems.accept.removeEventListener("click", handle.accept);
    //       elems.ignore.removeEventListener("click", handle.ignore);
    //     },
    //   };

    //   elems.accept.addEventListener("click", handle.accept);
    //   elems.ignore.addEventListener("click", handle.ignore);
    // }

    // if (storageGdpr === "accepted") consentRequiringActions();

    nav.addEventListener("click", function toggleNavActive() {
      const { classList } = nav;
      if ([].slice.call(classList).indexOf("nav--active") > -1)
        classList.remove("nav--active");
      else classList.add("nav--active");
    });

    window.addEventListener("scroll", function toggleHeaderPositioning() {
      if (window.pageYOffset > 350) header.classList.add("header--fixed");
      else header.classList.remove("header--fixed");
    });

    // function offsetAnchor() {
    //   if (window.location.hash.length !== 0) {
    //     window.scrollTo(window.scrollX, window.scrollY - 50);
    //   }
    // }

    // document
    //   .querySelectorAll('a[href^="#"]')
    //   .forEach((elem) =>
    //     elem.addEventListener("click", () =>
    //       window.setTimeout(() => offsetAnchor())
    //     )
    //   );

    // window.setTimeout(offsetAnchor);

    // function getFormData() {
    //   const entries = [].slice.call(formElem.elements);

    //   const data = entries.reduce(
    //     (acc, elem) => (elem.value ? { ...acc, [elem.name]: elem.value } : acc),
    //     {}
    //   );
    //   return JSON.stringify(data);
    // }

    // function submitForm() {
    //   const xhr = new XMLHttpRequest();
    //   xhr.open("POST", `.netlify/functions/sendMessage`);
    //   xhr.send(getFormData());
    //   xhr.addEventListener("load", () => {
    //     switch (xhr.status) {
    //       case 200:
    //         [].slice.call(formElem.elements).forEach(function clearElem(elem) {
    //           // eslint-disable-next-line no-param-reassign
    //           elem.value = "";
    //         });
    //         // this.handleSuccess(xhr);
    //         break;
    //       default:
    //         // eslint-disable-next-line no-alert
    //         alert(
    //           "Senden der Nachricht fehlgeschlagen.\nBitte versuche es später noch einmal oder kontaktiere uns unter kurs@so-kommunizieren.ch."
    //         );
    //         break;
    //     }
    //   });

    //   xhr.addEventListener("error", () => {
    //     // eslint-disable-next-line no-alert
    //     alert(
    //       "Senden der Nachricht fehlgeschlagen.\nBitte versuche es später noch einmal oder kontaktiere uns unter kurs@so-kommunizieren.ch."
    //     );
    //   });
    // }

    // document.querySelector("form").addEventListener("submit", submitForm);
  },
};
</script>

<style>
* {
  line-height: 1.3em;
}

a {
  text-decoration: none;
}

body {
  font-size: 2rem;
  font-weight: 300;
  margin: 0 auto;
  max-width: 900px;
}

button {
  font-size: inherit;
}

h1,
h1 *,
h2,
h3 {
  font-family: serif;
  font-weight: 300;
}

h1 {
  font-size: 5.236042rem;
}

h2 {
  font-size: 3.23606rem;
  text-align: center;
}

h3 {
  text-align: center;
}

html {
  font-family: sans-serif;
  font-size: 45%;
  font-size: clamp(45%, 1vw, 65%);
  scroll-behavior: smooth;
}

strong,
strong * {
  font-weight: 700;
}

textarea {
  font-family: inherit;
}

.footer {
  background-color: #966b40;
  box-sizing: border-box;
  padding: 10px;
  height: 90px;
  text-align: center;
  font-size: 1.23607rem;
  color: #ffffff;
}

.footer a {
  color: #ffffff;
  font-weight: 700;
}

.header {
  position: relative;
  display: flex;
  flex-direction: column;
}

.header--fixed {
  margin-bottom: 56px;
}

.header--fixed .header__content {
  left: 0;
  margin: auto;
  max-width: 900px;
  position: fixed;
  right: 0;
  z-index: 80;
}

.header__content {
  position: relative;
  background-color: #e5cdad;
  display: flex;
  justify-content: flex-end;
}

.header__emotion {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  flex-basis: 350px;
  opacity: 0.25;
  background-image: url(../assets/mother-father-and-baby-sepia.jpg);
}

.header__logo {
  width: 155px;
}

.header__home {
  height: 204px;
  position: absolute;
  left: 0;
  top: -144px;
}

.nav {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  color: #966b40;
  align-items: flex-end;
  padding: 12px;
  box-sizing: border-box;
  min-height: 56px;
}

.nav::before {
  width: 28px;
  height: 28px;
  margin-bottom: 2px;
  content: " ";
  background-image: url(../assets/menu-bars--brown.svg);
  cursor: pointer;
}

.nav.nav--active::before {
  background-image: url(../assets/close-24px--brown.svg);
  background-repeat: no-repeat;
  background-size: cover;
}

.nav--active .nav__entry {
  display: block;
}

.nav__entry {
  display: none;
  margin: 5px;
  text-align: right;
}

.nav__entry--2ndary {
  margin-right: 16px;
}

.nav__entry--primary {
  padding: 5px 10px;
  border: 1px solid #966b40;
  border-radius: 5px;
}

/* this rule is needed to override user agents stylesheets */
.nav a {
  color: #966b40;
}

@media screen and (min-width: 500px) {
  .header__emotion {
    margin-left: 0;
    width: 100%;
    overflow: hidden;
  }
}

@media screen and (min-width: 630px) {
  .nav:not(.nav--kurs) {
    flex-direction: row;
    align-items: center;
  }

  .nav:not(.nav--kurs)::before {
    display: none;
  }

  .nav:not(.nav--kurs) .nav__entry {
    margin: 0 10px;
    display: block;
  }
}
</style>
