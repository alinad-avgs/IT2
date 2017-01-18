Funksjoner
==========

**En funksjon er en samling med kode som kjøres når man henviser til funksjonen i et funksjonskall. Et funksjonskall kan for eksempel skje når man har en hendelse som å trykker på en knapp eller en meny. Man kan også utføre et funksjonskall i et program ved å skrive navnet på funksjonen.**

``` javascript
<input type="button" value="Trykk her" onclick="minFunksjon()">
En funksjon kan også kjøres ved å skrive navnet på funksjonen i programmet

for(var i=0;i<3;i++){
   minFunksjon();
}

function minFunksjon(){
   console.log("Dette er skrevet ut av en funksjon");
}
```

Tidsstyrte funksjoner
---------------------

Noen ganger kan det være behov for å kjøre en funksjon ved faste tidsintervall. Til dette brukes kommandoen setInterval. I eksempelet under kjøres funksjonen en gang hvert sekundet.

``` javascript
//Kjører funksjonen "minKlokke" for hvert 1000ms
var minVar=setInterval(function(){minKlokke()},1000);

function minKlokke()
{
var dato=new Date(); //Henter inn datoobjekt
var tid=dato.toLocaleTimeString();
console.log(tid + " " + dato);
}
```

Funksjoner med inn- og utparameter
----------------------------------

For å øke gjenbruksverdien til kode kan det være lurt å bruke funksjoner. Disse kan kjøres så mange ganger man ønsker, kun ved hjelp av et funksjonskall. For å øke nytteverdien til en funksjon, kan det være nyttig å sende med, og få tilbake behandlet data. I eksempelet under ganges to tall sammen ved å sende de med som paramtere i funksjonskallet.

```javascript
//Funksjonen ganger sammen to tall som er
//sendt med som innparameter.
//Resultatet returneres

function gangeToTall(a,b)
{
return a*b;
}

document.getElementById("demo").innerHTML=gangeToTall(4,3);
```

Hendelser
---------

I de aller fleste programmer ønsker man en interaktivitet mellom bruker og program. Dette kan for eksempel være at noe skjer når man trykker på en knapp. I HTML så finnes det mange ulike hendelsesatrubutter, men felles for dem alle er at de kjører en funksjon når ønsket hendelse skjer. I dette kurset kommer vi for det aller meste til å bruke hendelsesatributten "onclick". Denne kjører en valgfri funksjon når brukeren trykker på en knapp.

**Tips:**Ved å bruke hendelsesatributten _oncllick="minFunksjon()"_ på en knapp, vil programmet i funksjonen minFunksjon() kjøres hver gang denne trykkes.

innerHTML og getElementById
---------------------------

Vi har sett at kommandoen console.log skriver ut en melding i konsollvinduet. Som regel er det mer hensiktsmessig å skrive ut innhold direkte på siden. En måte å gjøre dette på er å bruke kommandoen document.getElementById med egenskapen innerHTML. Dette er en måte å få tak i, og endre innholdet til et element eller tagg i html-dokumentet.

For å fortelle datamaskinen hvilket element eller tagg vi ønsker å få tak i, brukes kommandoen _document.getElementById("mittElement")_. Den vil da lete etter et element med id-atributt som passer. I dette tilfellet vil det være taggen med id="mittElement".

HTML-koden i eksempelet under ligger i filen index.html, og inneholder en knapp med en hendelsesatributt og en tom div med id-atributt. Når brukeren trykker på knappen skrives det ut en beskjed med innerHTML i en div.

``` html
<!doctype html>
<html lang="nb">
<head>
	<meta charset="UTF-8">
	<title>Hendelser</title>
</head>
<body>
	<input id="minKnapp" type="button" value="Skriv ut">
	<div id="minDiv"></div>
  <script type="text/javascript" src="script.js"></script>
</body>
</html>

Rett opp til å unngå inline javascript.

```
I filen script.js ligger funksjonen med koden som kjøres når noen trykker på knappen.

``` javascript

// Leser inn knappeelementet
var knappElement = document.getElementById("minKnapp");

// Lytter på om noen har trykket på knappen.
knappElement.onclick = skrivUt;

function skrivUt(){
	document.getElementById("minDiv").innerHTML = "Du trykket på knappen!";
}
```





[/stextbox]