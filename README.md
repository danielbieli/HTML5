# HTML5

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
