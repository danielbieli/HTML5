# HTML5

## HTML Templates

### Minimal Valid HTML5 Markup

```html  
<!doctype html>
<html lang="de-CH">
    <head>
        <meta charset="utf-8">
        <title>Minimal Valid HTML5</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    <body>
    </body>
</html>
```

### Meta Refresh - HTML Weiterleitung

```html
<!doctype html>
<html lang="de">
    <head>
        <meta charset="utf-8">
	<meta name="robots" content="noindex, follow">
        <title>Meta Refresh</title>
	<meta http-equiv="refresh" content="0; URL=https://danielbieli.tk">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">	
    </head>
    <body>
    </body>
</html>
```

## `<head></head>`

### Meta Tags

#### META NAME="ROBOTS"

```html  
<meta name="robots" content="noindex, follow">
<meta name="robots" content="index, nofollow">
<meta name="robots" content="noindex, nofollow">
```

Gültige Werte für das Attribut "CONTENT" sind: "INDEX", "NOINDEX", "FOLLOW", "NOFOLLOW". Wenn es kein robots <META> -Tag gibt, ist der Standardwert "INDEX, FOLLOW". 
  
Dies ist auch korrekt so, da alles "Indexieren & Folgen" eigentlich immer gewünscht ist. Es ist viel weniger Arbeit nur die Ausnahmen zu markieren. Zum Beispiel externe Links sollten so aussehen:

##### Externer Link (Öffnen im neun Tab & nofollow)

```html
<a href="https://danielbieli.tk" target="_blank" rel="nofollow">Daniel Bieli</a>
```
 
##### `<meta name="robots" content="noindex, follow">`

Impressumseite (Soll Google nicht in Index aufnehmen, aber die Links auf der Seite trotzdem wete

##### `<meta name="robots" content="index, nofollow">`

Inhaltlich gute Seite mit nur externen Links. Wenn `nofollow` im Head angegeben wird, wird per default keinem Link mehr gefolgt.

##### `<meta name="robots" content="noindex, nofollow">`

Eine Login Seite zum Beispiel. Weder soll diese indexiert werden noch soll der Robot unser Crawl Guthaben verschwenden mit nicht öffentlichen Links.

#### [GEO Meta Tag](http://www.geo-tag.de/informator/de1.html)

Geo-Tags sind HTML-Meta-Tags, die eine Aussage über die geografische Lokation einer Webseite oder der ganzen Site machen. 

* [GEO Meta Tag Validator](http://www.geo-tag.de/validator/de.php)
* [GEO Meta Tag Generator](http://www.geo-tag.de/generator/de.html)

```html
<meta name="geo.region" content="CH-SO" />
<meta name="geo.placename" content="Solothurn" />
<meta name="geo.position" content="46.81819;8.22751" />
<meta name="ICBM" content="46.81819, 8.22751" />
```

### Skripte

#### JavaScript

**Async**: JS im Head sollte grundsätzlich immer async geladen werden, da es einfach nebem dem DOM Rendering laden ohne zu blockieren.
Ausnahme: JS Funktion Trigger wird bei async gerendert bevor die JS Funktion geladen wurde.

**Defe**r: JS wird erst als letztes geladem.

```html
<script src="demo_async.js" async></script>
<script src="demo_defer.js" defer></script>
<script src="demo.js"></script>
```

Fazit: Falls Funktionen schneller aufgerufen als geladen werden sollten Sie den Aufbau Ihrer Seite nochmals überdenken. 
