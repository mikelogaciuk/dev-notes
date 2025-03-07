# full-page-scrolling

## Wstęp

Ten styl nazywa się **full-page scrolling** lub **scroll snapping**. Jest popularny w nowoczesnym web designie, ponieważ pozwala na płynne przechodzenie między sekcjami, które zajmują cały ekran.

Aby osiągnąć taki efekt, możesz użyć CSS z właściwością `scroll-snap` lub bibliotek JavaScript, takich jak [fullPage.js](https://education.procreate.com/). Oto przykład, jak to zrobić za pomocą CSS:

```css
html,
body {
  height: 100%;
  margin: 0;
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
}

section {
  height: 100vh; /* Każda sekcja zajmuje 100% wysokości widoku */
  scroll-snap-align: start;
}
```

I w HTML:

```html
<body>
  <section style="background-color: lightblue;">Sekcja 1</section>
  <section style="background-color: lightgreen;">Sekcja 2</section>
  <section style="background-color: lightcoral;">Sekcja 3</section>
</body>
```

## Pozostałe

Aby osiągnąć efekt **full-page scrolling** za pomocą TailwindCSS, możesz skorzystać z klas takich jak `h-screen` (dla wysokości sekcji) oraz `snap-y` i `snap-mandatory` (dla efektu scroll snapping). Oto przykład:

### HTML

```html
<body class="snap-y snap-mandatory overflow-y-scroll">
  <section
    class="h-screen bg-blue-500 snap-start flex items-center justify-center"
  >
    <h1 class="text-white text-4xl">Sekcja 1</h1>
  </section>
  <section
    class="h-screen bg-green-500 snap-start flex items-center justify-center"
  >
    <h1 class="text-white text-4xl">Sekcja 2</h1>
  </section>
  <section
    class="h-screen bg-red-500 snap-start flex items-center justify-center"
  >
    <h1 class="text-white text-4xl">Sekcja 3</h1>
  </section>
</body>
```

### Wyjaśnienie:

1. **`h-screen`**: Każda sekcja zajmuje 100% wysokości widoku.
2. **`snap-y`**: Ustawia kierunek przewijania na pionowy.
3. **`snap-mandatory`**: Wymusza zatrzymanie przewijania na najbliższym elemencie.
4. **`snap-start`**: Ustawia punkt zatrzymania przewijania na początku każdej sekcji.

Dzięki temu każda sekcja wypełnia cały ekran, a przewijanie płynnie przechodzi między nimi. Jeśli chcesz dodać animacje przewijania, możesz użyć klasy `scroll-smooth` w `<html>`.
