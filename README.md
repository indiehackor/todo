# Før du starter

## node og npm
* Sjekk om du har node og npm. `node -v` og `npm -v` i terminalen.
* Hvis du ikke, [last ned node](https://nodejs.org/en/) eller installer med `brew install node`.

## Vue
* Kjør `npm install -g @vue/cli` (trengs strengt tatt ikke, men én dag!)
* Installer *Vue.js* Intellij plugin
* Clone repo
* Get to work.

# Todo app Oppgaver

## Innhold

1. Lag et skjema i App.vue med en input, label og en knapp

2. Lag en List komponent som tar inn en items prop.
    * Putt komponenten i App.vue

3. Lag en ListItem komponent som tar imot en todo prop
    * Putt en eller flere i ListItem og sjekk at det blir rendret riktig

### Tips
Du trenger ikke tenke så my på hva komponenter gjør enda.
Bare putt noe tull i de og sjekk om det rendres.

## Logikk

1. Opprett et `todoList` array som gis til *List* som prop
    * Opprett et `todoList` array i *App* sitt `data` object
    * Send `todoList` som prop til *List* via `items` prop'en
    
2. Rendre en *ListItem* for hver item inne i *List*
    * Bruk `v-for` til å rendre en *ListItem* for hver `item` i `items`, inne i *List*.
    * Send hvert `item` fra `items` listen inn i *ListItem* via todo prop'en
    * **tips**: `v-for` returnerer `index` for hver loop `v-for="(item, index) in items"`. Kanskje du trenger index?

3. Lag en `addItem` metode i *App*
    * Knytt verdien i inputfeltet til en verdi i `data`' ved å bruke `v-model`
    * Legg til en `addItem` metode på `methods` objektet i *App*
    * `this.todoList.push(...)` inn texten fra inputfeltet.
    * Kjør metoden når skjemaet submitter. (hint: `@submit`)

4. Hvis du ikke allerede har en slett knapp i *ListItem* er det på tide
    * Opprett `methods` objektet i *ListItem* og lag en metode som heter `deleteItem`. Sleng gjerne en `alert('it works')` inni der.
    * Legg til et `v-on` directive for klikk (forkortet `@click`) som kjører `deleteItem` metoden. Sjekk om `'it works'`.
    * Hvis `'it works'`, bytt ut alert med `this.$emit('delete-todo', index)`. Abrakadabra! [Custom events](https://vuejs.org/v2/guide/components-custom-events.html)!
    
    (*NB:* `index` kan sendes in som prop når du kjører v-for i *List*)
    
    **Merk:** `delete-todo` er et vilkårlig navn på en custom event.

5. Opprett en `removeItem` metode i *App*
    * Opprett en metode `removeItem` som sletter ett element fra `todoList` basert på index
    * *List* må ta imot `removeItem` via en prop, kanskje ved samme navn? Du velger
    * Denne kjøres når det forekommer en `delete-todo` event på *ListItem*, altså... drumroll.. `@delete-todo`!!


Nå skal du ha en liste hvor du kan legge til og slette ting.

Hvis ikke, sjekk ut losning branchen 😆

