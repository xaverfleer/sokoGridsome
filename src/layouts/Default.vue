<template>
  <div class="layout">
    <header class="header">
      <div class="header__emotion"></div>
      <div class="header__content">
        <a class="header__home" href="./index.html">
          <g-image
            alt="Logo mit Giesskanne, die den inneren Baum deines Kindes
          nährt."
            class="header__logo"
            src="~/assets/logo.png"
            title="Zur Startseite"
          />
        </a>
        <nav class="nav">
          <a
            class="nav__entry nav__entry--primary"
            href="./kurs.html"
            target="_blank"
            >Gratis starten</a
          >
          <a class="nav__entry nav__entry--2ndary" href="#contents">Inhalte</a>
          <a class="nav__entry nav__entry--2ndary" href="#offer">Angebot</a>
          <a class="nav__entry nav__entry--2ndary" href="#prizing">Preise</a>
          <a class="nav__entry nav__entry--2ndary" href="#about-us"
            >Über mich</a
          >
          <a class="nav__entry nav__entry--2ndary" href="#contact">Kontakt</a>
        </nav>
      </div>
    </header>
    <slot />
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

    // const header = document.querySelector(".header");
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

    // window.addEventListener("scroll", function toggleHeaderPositioning() {
    //   if (window.pageYOffset > 360) header.classList.add("header--fixed");
    //   else header.classList.remove("header--fixed");
    // });

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
body {
  font-family: source-sans-pro, sans-serif;
  margin: 0 auto;
  max-width: 900px;
}

.header {
  position: relative;
  display: flex;
  flex-direction: column;
}

/* .header--fixed {
  margin-bottom: 56px;
}

.header--fixed .header__content {
  position: fixed;
  top: 0;
  left: 8px;
  right: 8px;
  z-index: 80;
} */

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
  background-image: url(../assets/mother-father-and-baby.jpg);
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
  text-decoration: none;
}

@media screen and (min-width: 500px) {
  .header__emotion {
    margin-left: 0;
    width: 100%;
    overflow: hidden;
  }
}
</style>
