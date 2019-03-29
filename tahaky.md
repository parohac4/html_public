# HTML taháky

**Struktura html souboru**

```html
<html lang="cs">
<head>
  <title>title</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="popis webu"> 
  <meta name="keywords" content="klíčová slova">
  <meta name="robots" content="all">
  <meta name="googlebot" content="all">
  <meta name="author" content="Tomáš Jelínek">
  <link rel="shortcut icon" href="img/favicon.ico">
</head>
<body>
Test 1
    </body>
```

**Připojení externího stylu**

Přímo do stránky:

```html
<script type="text/javascript">
zápis javascriptu
</script>
```

Volání externího souboru:

```html
<script type="text/javascript" src="cesta/soubor.js"></script>
```

**Poznámky**

Poznámka v HTML:

```html
<!-- toto je poznámka v HTML --> a toto už ne
/* tohle taky ne */
// a tohle taky ne
Poznámka v CSS:
<style type="text/css">
/* toto je poznámka v CSS stylu */
// toto není poznámka v CSS
```


Poznámka v Javascriptu:

```
<script type="text/javascript">
/* toto je poznámka ve skriptu */
toto není poznámka // a tohle ano
// a toto taky
</script>
```

**Odkazy**

Odkaz do jiného webu musí obsahovat http:// (to je absolutní adresování). 
```html
<a href="http://www.seznam.cz">Seznam</a>
```

Odkaz na soubor stranka.html do stejného adresáře (bez http://, takže relativní adresování):

```html
<a href="stranka.html">Odkaz na stranka</a>
```

Odkaz na soubor stranka.html ležící v adresáři o úroveň výš (dvě tečky znamenají úroveň
výš):

```html
<a href="../stranka.html">Odkaz do vyššího adresáře</a>
```

Otevření odkazu do nového okna:

```html
<a href="stranka.html" target="_blank">odkaz do nového okna</a>
```

nebo

```html
<a href="http://www.seznam.cz" target="_blank">odkaz na Seznam do nového okna</a>
```

**Odkazy v HTML**

Záložky (kotvy, anchory)

Záložka někde v dokumentu:

```html
<a name="jmeno_zalozky"></a>
```

a po kliknutí na tento odkaz se na záložku po kliknutí odroluje:

```html
<a href="#jmeno_zalozky">odrolovat</a>
```

**Barvy stránky a odkazů**

Tag <style> patří mezi tagy <head> a </head>:

```html
<style type="text/css">
body {color: black; background-color: white; background-image: url("pozadi.gif");} /* text černý, barva
pozadí bílá, obrázek na pozadí */
a:link {color: blue;} /* nenavštívený odkaz */
a:visited {color: navy;}/* navštívený odkaz */
a:hover {color: red} /* odkaz, přes který se jede myší*/
</style>
```

Dříve se to dělalo pomocí atributů tagu <body>, to je zastaralé.


**Nadpisy**

```html
<h1>Nadpis nejvyšší úrovně</h1>
<h2>Nadpis kapitoly nebo odstavce</h2>
<h3>Podnadpis</h3>
...
<h6>Sedmička už nefunguje</h6>
```

**Odstavce a vynucené zalomení řádku**

```html
<p>Odstavec zalamuje řádky podle šířky prostoru, který má (nejčastěji okna). Na konci odstavce se
zalomí řádek.</p>
```

Je-li potřeba uvnitř odstavce zalomit řádek, použije se tag <br>, v normálních textech k tomu
ale není důvod:

```html
<p>Text odstavce plyne<br> a najednou se zalomí řádek.</p>
```

**Zarovnání odstavce**

Normálně se odstavce (i jiné tagy) zarovnávají doleva. Zarovnání jednoho odstavce doprava:

```html
<p style="text-align: right">Odstavec zarovnaný doprava.</p>
```

Zarovnání na střed a do bloku:

```html
<p style="text-align: center">Odstavec zarovnaný na střed.</p>
<p style="text-align: justify">Odstavec zarovnaný do bloku.</p>
```

Lepší je ale nastavit všechny odstavce najednou globálním stylem:

```html
<style type="text/css">
p {text-align: center;} /* všechny odstavce budou zarovnány na střed */
address {text-align: right;} /* tag address bude zarovnán doprava */
.doleva {text-align: left} /* ale tag, který bude v sobě mít class="doleva", se bude zarovnávat doleva */
</style>
```

**Nastavení fontu**


```html
<span style="font-family: Arial, sans-serif">Text arialem</span>
```


nebo použití na odstavec:
```html
<p style="font-family: Arial, sans-serif">Odstavec arialem</p>
```


dá se použít na každý tag, třeba i na body, což ovlivní celou stránku:

```html
<body style="font-family: Arial">
```


Lepší je to ale zapsat globálně stylem do hlavičky:

```html
<style type="text/css">
body {font-family: Arial, sans-serif;}/* pro celý dokument /*
p {font-family: "Times New Roman", serif} /* pro všechny odstavce <p>*/
.trida {font-family: Verdana, sans-serif} /* pro všechny tagy s class="trida" */
</style>
```

Víceslovné názvy písem musejí být v uvozovkách.


**Barva písma**

```html
<span style="color: red;">Červené písmo</span>
```

nebo třeba pro odstavec

```html
<p style="color: blue">Odstavec modrým písmem</p>
```

Dá se to napsat do libovolného tagu, ale nemusí to fungovat u odkazů (tag <a>), u nich se to
musí udělat globálním stylem <style>, což je ale stejně lepší i v jiných případech:

```html
<style type="text/css">
body {color: maroon; background-color: white;}/* hnědé písmo pro celý dokument, barva pozadí bílá /*
p {color: green;} /* zelené písmo pro všechny odstavce <p> */
.zlute {color:yellow;} /* pro všechny tagy s class="zlute" */
a:link {color: blue;} /* nenavštívený odkaz modrý*/
a:visited {color: navy;}/* navštívený odkaz tmavě modrý */
a:hover {color: red} /* odkaz, přes který se jede myší červený */
</style>
```

**Tučnost, kurzíva**

```php+HTML
<b>Tučné písmo</b>
<i>Kurzíva</i>
```
Normální písmo, <b>tučné písmo, <i>tučná kurzíva</i></b>, <i>normální kurzíva</i>.
<strong>také tučné písmo (zvýraznění)</strong>
<em>také kurzíva (zvýraznění)</em>
```

**Podrtžení **



Podtržený text

Ale nepoužívejte to, plete se to s odkazem. Taky se to blbě čte.

​```html
<span style="text-decoration: underline">podtržení pomocí stylu</span>
```

také doporučuji nepoužívat.

Odkazy se podtrhávají automaticky:

```html
<a href="soubor.html">automaticky podtržený odkaz</a>
```

Jak zrušit podtrhávání odkazů:

```html
<style type="text/css">
a {text-decoration: none;}
a: hover {text-decoration: underline;}
</style>
```

**Obrázek**

Obrázek ze stejného adresáře, ve kterém je html stránka:

```php+HTML
<img src="obrazek.gif" width="100" height="200" alt="obrázek">
```

nebo obrazek.jpg nebo obrazek.png. Zadané rozměry by měly být skutečné rozměry obrázku
(jednotka se v HTML neuvádí, ale rozměry jsou v pixelech = obrazovkových bodech).

Obrázek z nadřazeného adresáře (to jsou ty dvě tečky):

```html
<img src="../obrazek.gif" width="100" height="200" alt="obrázek">
```

Obrázek z webu (absolutní adresa, začíná http://):
```
<img src="http://www.jakpsatweb.cz/images/jakpw.gif" width="100" height="200" alt="obrázek">
```

Obrázek fungující jako odkaz (kliká):

```html
<a href="cilova_stranka.html"><img src="obrazek.gif" width="100" height="200" alt="obrázek"></a>

Obrázek fungující jako odkaz, ale bez modrého rámečku:

​```html
<a href="cilova_stranka.html"><img src="obrazek.gif" width="100" height="200" alt="obrázek"
border="0"></a>
```

**Seznamy**


Odrážkový seznam (puntíky):

```html
<ul>
<li>první položka</li>
<li>druhá položka</li>
</ul>
```

Obrázkové odrážky se dělají stejně jako puntíky, ale přidává se styl:

```html
<style type="text/css">
ul li {list-style-image: url("obrazek.gif"}
</style>
```

Seznamy v HTML (odrážky a číslování), List-style-image
Číslovaný seznam:

```html
<ol>
<li>první položka, čísluje se to automaticky</li>
<li>druhá položka</li>
</ol>
```

Jiný typ číslování, třeba a) b) c):

```html
<style type="text/css">
ol li {list-style-type: lower-alpha;}
</style>
```

**Div = oddíl**


Tag div slouží nejčastěji na obalení více blokových prvků. Například když budu chtít mít tři
odstavce červeným písmem a odsazené zleva o 30px:

```html
<div style="color: red; margin-left: 30px;">
<p>odstavec</p>
<p>odstavec</p>
<p>odstavec</p>
<div>
```


Ale dá se to dělat samozřejmě i jinak, stejně tak <div> má širší použití, většinou na rozvržení
designu stránky.


**Rozvržení stránky**


Rozvržení stránky se dá dělat desítkami různých způsobů. Toto je jen příklad:

```html
<body>
<div id="cela-stranka">
<div id="hlavicka">
```

Hlavička

```html
</div>
<div id="leve-menu">
```

Levé menu

```html
</div>
<div id="hlavni-text">
```

Hlavní text

```html
</div>
<div id="paticka">
```

Patička

```html
</div>
</div>
</body>
```

a k tomu se dá napsat styl mnoha a mnoha různými způsoby. 

Příklad stránky s pevnou
šířkou:

```html
<style type="text/css">
body {text-align: center; }
#cela-stranka {width: 760px; margin: 0px auto;}
#leve-menu {width: 160px; float: left;}
#hlavni-text {width: 500px; float: left;}
#paticka {clear: left;}
</style>
```

Ta mříž # se vždycky vztahuje k prvku se stejným id=.

Návod na centrování [celé stránky](https://jakpsatweb.cz/centrovani-stranky.html).


**Tabulky**

Nejjednodušší tabulka 2x2:

```html
<table cellspacing="0">
<tr>
<td>První buňka prvního řádku</td>
<td>Druhá buňka prvního řádku</td>
</tr>
<tr>
<td>První buňka druhého řádku</td>
<td>Druhá buňka druhého řádku</td>
</tr>
</table>
```


Zapnutí rámečku (border) a vnitřních okrajů buněk (cellpadding):

```html
<table border="1" cellpadding="6" cellspacing="0">...
```

Jednoduchý rámeček (nebude dvojitý):

```html
<table border="1" style="border-collapse: collapse;">
<tr>první buňka...<td></td><td></td></tr>
<tr><td></td><td></td></tr>
</table>
```

Buňka přes dva řádky (v druhém řádku se zapíše o jednu buňku méně):

```html
<td rowspan="2">buňka přes dva řádky</td>
```

Buňka přes tři sloupce:

```html
<td colspan="3">Buňka přes tři sloupce</td>.
```


**Iframe**


Do stránky se vloží obdélník a v něm se zobrazí jiná stránka:

```html
<iframe src="jina-stranka.html" width="300" height="400" name="vnoreny">
alternativní text
</iframe>
```


**Bublina na přejetí myší**


Do libovolného tagu stačí napsat atribut title="text bubliny", například:

```html
<span title="text, který se objeví ve žluté bublině">text, přes který když se přejede myší, se to
objeví</span>
```


**Přesměrování**


Jediné pořádné přesměrování se nedá udělat v HTML, nýbrž na serveru (v .htaccess nebo
programovat). Níže popsané metody jsou jenom náhražky.


Přesměrování meta tagem, čeká to 2 sekundy:

```html
<meta http-equiv="refresh" content="2;URL=http://www.nekam.cz/cesta/soubor.html">
```

Přesměrování javascriptem:

```html
<script type="text/javascript">
top.location.href="http://www.nekam.cz/cesta/soubor.html";
</script>
```

**Stažení souboru**

Třeba soubory .docx, .avi a podobné. Normálně odkazem na ten soubor:

```html
<a href="pisemka.docx">stáhnout písemku</a>
```

Nechat stáhnout soubory, které prohlížeče interpretují (třeba .html nebo .js) můžete tak, že je
zabalíte do .zip nebo do .rar. To se hodí i na stažení více souborů najednou:

```html
<a href="archiv.zip">stáhnout archiv</a>
```

Stahované soubory je samozřejmě nutné umístit na server.


Zdroj: [jakpsatweb.cz](https://www.jakpsatweb.cz/html/html-tahak.html)

