# intro
In dit korte artikel zullen we de basisprincipes van het Svelte-framework bespreken. We zullen kijken naar wat het framework inhoudt en hoe we het kunnen toepassen in onze ontwikkelingsprojecten.

# Wat is Svelte?
Svelte is inderdaad een echt reactief framework, en dit komt doordat het op een heel andere manier is opgebouwd dan bijvoorbeeld React. In tegenstelling tot React maakt Svelte geen gebruik van een virtuele DOM en een `setState`-methode. In plaats daarvan controleert Svelte of variabelen opnieuw worden toegewezen met behulp van de toewijzingsoperator.

Dit unieke aspect van Svelte zorgt ervoor dat het niet telkens de DOM-structuur hoeft te doorlopen en nieuwe nodes met de vorige nodes hoeft te vergelijken. Dit komt doordat Svelte al tijdens het compilatieproces precies weet welke variabelen moeten worden bijgewerkt. Hierdoor kan Svelte op efficiënte wijze alleen de benodigde wijzigingen in de DOM aanbrengen.

Dankzij deze optimalisaties en de kennis die Svelte al heeft tijdens het compilatieproces, kan het framework zeer reactief en performant werken, waardoor het een aantrekkelijke keuze is voor het ontwikkelen van moderne webapplicaties.

# Hoe kan ik Svelte gebruiken?
Installatie en opzet van Svelte: uitleg van de verschillende installatieopties, inclusief npm en de Svelte REPL (Read-Eval-Print Loop).
Om lokaal een project te maken, beginnen we met SvelteKit, het officiële applicatieframework van het Svelte-team:
```
npm create svelte@latest myapp
cd myapp
npm install
npm run dev
```
Het project structure komt dit zo te staan:
```
my-project/
├ src/
│ ├ lib/
│ │ ├ server/
│ │ │ └ [your server-only lib files]
│ │ └ [your lib files]
│ ├ params/
│ │ └ [your param matchers]
│ ├ routes/
│ │ └ [your routes]
│ ├ app.html
│ ├ error.html
│ ├ hooks.client.js
│ └ hooks.server.js
├ static/
│ └ [your static assets]
├ tests/
│ └ [your tests]
├ package.json
├ svelte.config.js
├ tsconfig.json
└ vite.config.js
```
En de component format wordt zo beschrijven waar elke html code gaat zijn stijlen en js events nemen volgens de script en css code die in zijn eigen component file staan.
Dit maakt het moeilijk om te conflicteren met codecommando's, zelfs als ze dezelfde naam hebben
```
<script>
	// logic goes here
</script>

<!-- markup (zero or more items) goes here -->

<style>
	/* styles go here */
</style>
```
## Hoe kan ik de components van een pagina gebruiken?
Je moet de component importeren van zijn file en dan kun je him in de pagina gebruiken.

Een tag in kleine letters, zoals ```<div>```, geeft een regulier HTML-element aan. Een tag met een hoofdletter, zoals ```<Widget>``` of ```<Namespace.Widget>```, geeft een component aan.
```
<script>
	import Widget from './Widget.svelte';
</script>

<div>
	<Widget/>
</div>
```

# Note
Als u problemen ondervindt bij het niet herkennen van de variabele die in het script wordt genoemd, dan raad ik u aan om TypeScript te gebruiken om het probleem op te lossen.

# Voordelen van Svelte ten opzichte van andere frameworks
- Verbeterde prestaties door het genereren van optimale, framework-vrije JavaScript-code tijdens het compilatieproces.
- Efficiënt gebruik van systeembronnen door het ontbreken van een virtuele DOM.
- Compacte bestandsgrootte van Svelte-applicaties.
- Eenvoudige en intuïtieve syntaxis voor het maken van componenten.
- Goede TypeScript-ondersteuning.

# Voorbeeld
[Meesterproef-2023](https://github.com/DutchEllie/meesterproef-2223)

# Bronnen
   - https://svelte.dev/docs#before-we-begin
   - https://kit.svelte.dev/docs/building-your-app
   - https://beeproger.com/blog/wat-is-svelte/
