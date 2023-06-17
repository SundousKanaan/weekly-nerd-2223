# Intro
In dit artikel gaan we het hebben over iets dat al lang had moeten wachten en dat het bouwen van responsive websites veel gemakkelijker zal maken en het is **containerquery's** 🔥

# Container queries
CSS-containerquery's stellen ons in staat om elementen te stylen op basis van de grootte van hun ouder- of containerelement. In tegenstelling tot mediaquery's, die de viewport gebruiken, richten containerquery's zich specifiek op de container waarin een element zich bevindt. Hierdoor kunnen we responsieve ontwerpen creëren die nauwkeurig reageren op de context van het element binnen de paginahierarchie.

# Hoe kan ik de Container queries gebruiken?
Om de container queries te gebruiken in css moeten we de parent container een type en name tegelijk geven:

```css
.section{
   .
   .
   container: card / inline-size;
}
```
Container types:
   - normal
      -  Het element is geen querycontainer voor query's op containergrootte, maar blijft een querycontainer voor query's in containerstijl.
   - size
      - We kunnen specifieke stijlregels toepassen op een element wanneer de grootte van de directe container bepaalde voorwaarden vervult. Dit stelt ons in staat om responsieve ontwerpen te maken die zich aanpassen aan de beschikbare ruimte binnen de container.
   - inline-size:
      -  Brengt een querycontainer tot stand voor dimensionale query's op de inline-as van de container. Past lay-out, stijl en insluiting van inline-formaat toe op het element.


**Nu gaan we aan de child elementen werken:**
Eerste moeten we de standaard stijlen bouwen:
```css
.section-child{
   .
   .
   background-color: red;
}
```
Daarna bouwen we de container query met de nieuwe stijlen in.Het is niet nodig om de alle stijlen te herschrijven, maar we hoeven alleen het stijl te vermelden waaraan wijzigingen moeten worden aangebracht.
```css
@container (max-width: 400px) {
 .section-child {
     background-color: blue;
 }
}
```
# Voordelen
 1. Contextuele styling: Elementen kunnen direct worden gestyled op basis van de grootte van hun container, waardoor nauwkeurige contextuele vormgeving mogelijk is.
 2. Herbruikbare componenten: Componenten kunnen zich aanpassen aan verschillende lay-outs zonder specifieke mediaquery's nodig te hebben.
 3. Vereenvoudigd ontwerp en onderhoud: Responsieve lay-outs kunnen eenvoudiger worden ontworpen en onderhouden doordat de focus ligt op de containercontext van elementen.
 4. Meer controle over elementen: Granulaire controle over de stijl van elementen op basis van de containergrootte voor een betere gebruikerservaring.

# Voorbeelden
   - [Card door Una Kravets](https://codepen.io/web-dot-dev/pen/ZEMzNGj)
   - [Valentine door Una Kravets](https://codepen.io/web-dot-dev/pen/rNrbPQw)
   - [website door Håvard](https://lynnandtonic.com/)
      - [Håvard on twitter](https://twitter.com/brynjulfs1?t=d3yxkNRDwWa_XyZ4YzsUVuAxEVzbWHctaOJiyDEYiG8&s=09)

# Bronnen
   - https://blog.logrocket.com/css-container-queries-guide/#:~:text=CSS%20container%20queries%20allow%20us,the%20style%20to%20an%20element.
   - https://web.dev/cq-stable/
   - https://developer.mozilla.org/en-US/docs/Web/CSS/container-type
