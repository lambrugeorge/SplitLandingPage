# 🚀 Split Landing Page

![Demo](SplitLandingPage.png)

Welcome to our world divided between Playstation 5 and Xbox Series X! A modern and interactive design that will capture your attention.

## 👀 Demo

Check out the [project demo here](link_to_demo).

## 💻 Technologies Used

- HTML5
- CSS3 (with CSS variables for easy customization)
- JavaScript

## ✨ Features

- **Interactive Design:** Animated and captivating for an unforgettable user experience.
- **Responsive:** Looks great on any device - from smartphones to large screens.
- **Dynamic Split:** The visible portion dynamically adjusts based on user actions.

## 🚀 How to Use

1. Clone this repository:

   ```bash
   git clone https://github.com/username/split-landing-page.git


User
root in css ce face imi poti explica conceptul?
ChatGPT
În contextul CSS (Cascading Style Sheets), termenul "root" se referă la rădăcina arborelui DOM (Document Object Model) al paginii web. Adică, este vorba despre elementul HTML rădăcină, care încapsulează întregul conținut al paginii.

Selectorul :root este folosit pentru a face referire la rădăcina documentului, ceea ce face posibilă definirea unor variabile CSS globale. Variabilele CSS sunt denumite și "custom properties" și încep cu prefixul "--". Ele sunt utile pentru a stoca valori care pot fi refolosite în întregul stylesheet.

Exemplu:

css
Copy code
:root {
  --culoare-primara: #3498db;
  --marime-font: 16px;
}

body {
  color: var(--culoare-primara);
  font-size: var(--marime-font);
}
În acest exemplu, am definit două variabile globale (--culoare-primara și --marime-font) în rădăcina documentului folosind selectorul :root. Aceste variabile pot fi apoi folosite în interiorul regulilor CSS pentru a aplica acele valori la diferite proprietăți ale elementelor.

Folosirea var(--nume-variabila) este modalitatea de a accesa valorile variabilelor în CSS. Este un mod eficient de a gestiona și actualiza valori comune într-un stylesheet.

User
la ce mai poate fi folosit?
ChatGPT
Selectorul :root și variabilele CSS pot fi folosite într-o varietate de moduri în proiectele web. Iată câteva exemple:

Gestionarea culorilor și dimensiunilor:

css
Copy code
:root {
  --culoare-primara: #3498db;
  --marime-font: 16px;
}

body {
  color: var(--culoare-primara);
  font-size: var(--marime-font);
}
Stilizarea cu media queries:

css
Copy code
@media (min-width: 768px) {
  :root {
    --marime-font: 18px;
  }
}

@media (min-width: 1200px) {
  :root {
    --marime-font: 20px;
  }
}
În acest exemplu, dimensiunea fontului poate varia în funcție de lățimea ferestrei browser-ului.

Stilizarea cu pseudoclase:

css
Copy code
:root {
  --culoare-link: #3498db;
}

a {
  color: var(--culoare-link);
}

a:hover {
  color: darken(var(--culoare-link), 10%);
}
Aici, culoarea unui link și culoarea la hover sunt definite folosind variabile.

Utilizarea în JavaScript:
Variabilele CSS definite în :root pot fi accesate și actualizate utilizând JavaScript. Acest lucru oferă o modalitate eficientă de a comunica între stilurile CSS și codul JavaScript.

javascript
Copy code
document.documentElement.style.setProperty('--culoare-primara', '#ff5733');
Această linie de cod actualizează valoarea variabilei --culoare-primara din CSS.

Crearea unui temă întunecată/luminoasă:

css
Copy code
:root {
  --culoare-background: #fff;
  --culoare-text: #333;
}

body {
  background-color: var(--culoare-background);
  color: var(--culoare-text);
}

body.dark-mode {
  --culoare-background: #333;
  --culoare-text: #fff;
}
Prin adăugarea clasei dark-mode la elementul body, temele întunecate și luminoase pot fi schimbate ușor.

Acestea sunt doar câteva exemple, dar capacitatea de a utiliza variabile CSS și selectorul :root aduce flexibilitate și organizare în proiectele web. Ele pot fi esențiale pentru menținerea și gestionarea stilurilor într-un mod coerent și ușor de întreținut.

User
* {
    box-sizing: border-box;
}

:root {
    --left-bg-color: rgba(87, 84, 236, 0.7);
    --right-bg-color: rgba(43, 43, 43, 0.8);
    --left-btn-hover-color: rgba(87, 84, 236, 1);
    --right-btn-hover-color: rgba(28, 122, 28, 1);
    --hover-width: 75%;
    --other-width: 25%;
    --speed: 1000ms;
}

body {
    font-family: 'Roboto', sans-serif;
    height: 100vh;
    overflow: hidden;
    margin: 0;
}

h1 {
    font-size: 4rem;
    color: #fff;
    position: absolute;
    left: 50%;
    top: 20%;
    transform: translateX(-50%);
    white-space: nowrap;
}

.btn {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 50%;
    top: 40%;
    transform: translateX(-50%);
    text-decoration: none;
    color: #fff;
    border: #fff solid 0.2rem;
    font-size: 1rem;
    font-weight: bold;
    text-transform: uppercase;
    width: 15rem;
    padding: 1.5rem;
    background-color: transparent; /* Adăugat pentru a asigura transparența la început */
    transition: background-color 0.3s ease; /* Adăugat pentru o tranziție lină a culorii de fundal */
}

.btn:hover {
    background-color: var(--left-btn-hover-color);
    border-color: var(--left-btn-hover-color);
}

.split.right .btn:hover {
    background-color: var(--right-btn-hover-color);
    border-color: var(--right-btn-hover-color);
}

.container {
    position: relative;
    width: 100%;
    height: 100%;
    background: #333;
}

.split {
    position: absolute;
    width: 50%;
    height: 100%;
    overflow: hidden;
}

.split.left {
    left: 0;
    background: url('Playstation.jpg');
    background-repeat: no-repeat;
    background-size: cover;
}

.split.left::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: var(--left-bg-color); /* Adăugat pentru transparență la început */
}

.split.right {
    right: 0;
    background: url('Xseries.jpg');
    background-repeat: no-repeat;
    background-size: cover;
}

.split.right::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: var(--right-bg-color); /* Adăugat pentru transparență la început */
}

.split.right, 
.split.left, 
.split-right::before, 
.split.left::before {
    transition: all var(--speed) ease-in-out ;
}




.hover-left .left {
    width: var(--hover-width)
}

.hover-left .right {
    width: var(--other-width)
}


.hover-right .right {
    width: var(--hover-width)
}

.hover-right .left {
    width: var(--other-width)
}

@media (max-width: 800px) {
    h1 {
        font-size: 2rem;
        top: 30%;
    }

    .btn {
        padding: 1.2rem;
        width: 12rem;
    }
} 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Split landing page</title>
</head>
<body>
    <div class="container">
        <div class="split left">
            <h1>Playstation 5</h1>
            <a href="#" class="btn">Buy Now</a>
        </div>
        <div class="split right">
            <h1>Xbox Series X</h1>
            <a href="#" class="btn">Buy Now</a>
        </div>
    </div>

<script src="script.js"></script>
</body>
</html>


vreau sa adaug acest proiect pe github imi poti creea un readMe foarte frumos inovativ sa ii dea pe spate celor care se vor uita sa fie la curent cu noutati 
ChatGPT
Cu plăcere! Iată un șablon pentru fișierul README.md care poate fi folosit pentru proiectul tău pe GitHub:

markdown
Copy code
# Split Landing Page

![Demo](link_la_imaginea_demo_github)

O pagină de destinație cu un design modern, împărțită în două părți, prezentând două produse diferite: Playstation 5 și Xbox Series X.

## Demo

Vizualizați o [demo a proiectului aici](link_la_demo).

## Tehnologii utilizate

- HTML5
- CSS3 (utilizând variabile CSS)
- JavaScript

## Caracteristici

- **Design Interactiv:** Interacțiunea utilizatorului este îmbunătățită prin animații și tranziții fluide.
- **Responsive:** Pagina este optimizată pentru a fi vizualizată pe dispozitive de diferite dimensiuni.
- **Împărțire dinamică:** Utilizarea JavaScript permite schimbarea dinamică a lățimii părții vizibile în funcție de interacțiunea utilizatorului.

## Cum să folosești

1. Clonează acest repository:

   ```bash
   git clone https://github.com/username/split-landing-page.git
Deschide fișierul index.html într-un browser web pentru a vedea pagina de destinație.
Contribuții
Contribuțiile sunt binevenite! Dacă aveți sugestii pentru îmbunătățiri sau găsiți probleme, vă rugăm să creați un issue sau să trimiteți un pull request.

Autor
Numele tău aici

Licență
Acest proiect este licențiat sub Licența MIT.

Nota: Acest proiect a fost creat ca parte a Proiectului de Split Landing Page.

less
Copy code

Asigură-te că înlocuiești "username" cu numele tău de utilizator GitHub și actualizează legăturile (`link_la_imaginea_demo_github`, `link_la_demo`, `link_la_licenta`, `link_la_proiect`) cu informațiile corespunzătoare. De asemenea, adaugă numele tău sub secțiunea "Autor". Acest șablon oferă o prezentare simplă și clară a proiectului tău.
User
dar cu emoji si text surpinzator poti reincerca sa il reproduci sa fie frumos de citit design inovativ si ce mai consideri a sa fie clean si la obiect de citit sa nu se plictiseasca cititorul 
ChatGPT
Cu siguranță! Iată o versiune mai inovatoare și mai plină de viață a fișierului README.md:

markdown
Copy code
# 🚀 Split Landing Page

![Demo](link_la_imaginea_demo_github)

Bun venit în lumea noastră împărțită între Playstation 5 și Xbox Series X! Un design modern și interactiv care îți va captiva atenția.

## 👀 Demo

Vizualizați o [demo a proiectului aici](link_la_demo).

## 💻 Tehnologii utilizate

- HTML5
- CSS3 (cu variabile CSS pentru un stil ușor de personalizat)
- JavaScript

## ✨ Caracteristici

- **Design Interactiv:** Animat și captivant pentru o experiență de utilizare de neuitat.
- **Responsive:** Arată bine pe orice dispozitiv - de la smartphone-uri la ecrane mari.
- **Împărțire Dinamică:** Lățimea părții vizibile se adaptează inteligent la acțiunile utilizatorului.

## 🚀 Cum să folosești

1. Clonează acest repository:

   ```bash
   git clone https://github.com/username/split-landing-page.git
Deschide fișierul index.html în browser pentru a experimenta pagina de destinație.
🤝 Contribuții
Contribuțiile tale sunt valoroase! Dacă ai sugestii sau găsești probleme, te rugăm să deschizi un issue sau să trimiți un pull request.

🌟 Autor
Numele tău aici

📝 Licență
Acest proiect este licențiat sub Licența MIT.

Nota: Proiectul a fost creat cu drag pentru Proiectul de Split Landing Page. Hai să aducem împreună această experiență în lume!

less
Copy code

Acest șablon utilizează emoji-uri, termeni expresivi și stil ușor de citit pentru a oferi un ton mai prietenos și dinamic. Asigură-te că înlocuiești "username" cu numele tău de utilizator GitHub și actualizează legăturile (`link_la_imaginea_demo_github`, `link_la_demo`, `link_la_licenta`, `link_la_proiect`) cu informațiile corespunzătoare.
User
![Demo](link_la_imaginea_demo_github) ce inseamna asta?
ChatGPT
În markdown, ![Demo](link_la_imaginea_demo_github) reprezintă o sintaxă pentru a insera o imagine într-un document. În această construcție:

Demo este textul alternativ (alt text) pentru imagine. Este afișat dacă imaginea nu poate fi încărcată sau pentru utilizatorii cu cititoare de ecran.
(link_la_imaginea_demo_github) reprezintă sursa imaginii. Înlocuiește acest text cu linkul real către imaginea demo a proiectului pe GitHub.
De exemplu, dacă imaginea demo este stocată într-un director numit images în repository și se numește demo.png, atunci link-ul ar putea arăta ceva de genul:

markdown
Copy code
![Demo](images/demo.png)
Asigură-te că imaginea este disponibilă și poate fi accesată în mod public pe GitHub, astfel încât oricine vizualizează fișierul README.md să poată vedea imaginea demo asociată proiectului.

User
ce imagine?
ChatGPT
Îmi pare rău pentru confuzie. Când am menționat ![Demo](link_la_imaginea_demo_github) în șablonul pentru README.md, m-am referit la locul în care poți adăuga un link către o imagine care ilustrează cum arată proiectul tău. Aceasta este opțională și poate fi utilă pentru a oferi o vedere rapidă a aspectului proiectului.

Dacă nu ai o imagine specifică pe care vrei să o adaugi în README.md, poți să ignori acea parte a șablonului sau să adaugi mai târziu o imagine relevantă care arată proiectul tău în acțiune.

Dacă într-adevăr nu dorești să adaugi o imagine la momentul actual, poți șterge linia respectivă sau să o înlocuiești cu un text descriptiv, cum ar fi:

markdown
Copy code
# 🚀 Split Landing Page

Bun venit în lumea noastră împărțită între Playstation 5 și Xbox Series X! Un design modern și interactiv care îți va captiva atenția.

## 👀 Demo

Vizualizați o [demo a proiectului aici](link_la_demo).
Acest text simplu și clar poate fi de ajuns în lipsa unei imagini demo specifică.

User
in folderul din github am adaugat imaginea .png un screenshot SplitLandingPage.png ce link atasez aici? ![Demo](link_la_imaginea_demo_github)
ChatGPT
Excelent! Dacă imaginea SplitLandingPage.png este în același director cu fișierul README.md în repository-ul GitHub, atunci link-ul ar trebui să arate astfel:

markdown
Copy code
![Demo](SplitLandingPage.png)
GitHub va gestiona automat imaginea și o va afișa în README.md. Asigură-te că imaginea este urcată pe GitHub și că numele fișierului este exact cel specificat în link. Dacă imaginea se află într-un alt director, asigură-te să incluzi calea corectă în link.

User
in engleza te rog 
markdown
Copy code
# 🚀 Split Landing Page

![Demo](link_la_imaginea_demo_github)

Bun venit în lumea noastră împărțită între Playstation 5 și Xbox Series X! Un design modern și interactiv care îți va captiva atenția.

## 👀 Demo

Vizualizați o [demo a proiectului aici](link_la_demo).

## 💻 Tehnologii utilizate

- HTML5
- CSS3 (cu variabile CSS pentru un stil ușor de personalizat)
- JavaScript

## ✨ Caracteristici

- **Design Interactiv:** Animat și captivant pentru o experiență de utilizare de neuitat.
- **Responsive:** Arată bine pe orice dispozitiv - de la smartphone-uri la ecrane mari.
- **Împărțire Dinamică:** Lățimea părții vizibile se adaptează inteligent la acțiunile utilizatorului.

## 🚀 Cum să folosești

1. Clonează acest repository:

   ```bash
   git clone https://github.com/username/split-landing-page.git
Deschide fișierul index.html în browser pentru a experimenta pagina de destinație.
🤝 Contribuții
Contribuțiile tale sunt valoroase! Dacă ai sugestii sau găsești probleme, te rugăm să deschizi un issue sau să trimiți un pull request.

🌟 Autor
Numele tău aici

📝 Licență
Acest proiect este licențiat sub Licența MIT.

Nota: Proiectul a fost creat cu drag pentru Proiectul de Split Landing Page. Hai să aducem împreună această experiență în lume!

less
Copy code

Acest șablon utilizează emoji-uri, termeni expresivi și stil ușor de cit
ChatGPT
markdown
Copy code
# 🚀 Split Landing Page

![Demo](SplitLandingPage.png)

Welcome to our world divided between Playstation 5 and Xbox Series X! A modern and interactive design that will capture your attention.

## 👀 Demo

Check out the [project demo here](link_to_demo).

## 💻 Technologies Used

- HTML5
- CSS3 (with CSS variables for easy customization)
- JavaScript

## ✨ Features

- **Interactive Design:** Animated and captivating for an unforgettable user experience.
- **Responsive:** Looks great on any device - from smartphones to large screens.
- **Dynamic Split:** The visible portion dynamically adjusts based on user actions.

## 🚀 How to Use

1. Clone this repository:

   ```bash
   git clone https://github.com/username/split-landing-page.git


Open the index.html file in a browser to experience the landing page.
🤝 Contributions
Your contributions are valuable! If you have suggestions or find issues, please open an issue or submit a pull request.

🌟 Author
Lambru Adrian Georgian


