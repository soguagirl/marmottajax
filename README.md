MarmottAjax
=========

Envoyer et recevoir des informations simplement en JavaScript avec MarmottAjax.

  - Tiny : 1.5ko minified
  - Simple
  - Ajax is Magic


> L'AjaxMarmotte de Dimou il est trop bien ! :D
> — *[Jeremy](https://twitter.com/jeremy__fr/status/473053329787211778)*

![Logo](https://raw.githubusercontent.com/marmottes/marmottajax/master/image.jpg "logo")

Exemple simple
----

Recuperer le contenu d'un fichier "foo.txt" :

```javascript
marmottajax("foo.txt").then(function(result) {
    alert(result);
});
```

Exemple Json
----

Recuperer le contenu du fichier json "marmottes.json" parsé :

```javascript
marmottajax.json("marmottes.json").then(function(marmottes) {
	console.log(marmottes);
}).error(function(message) {
	console.error(message);
});
```

Exemple de POST php
----

Envoyer des données avec la méthode POST :

```javascript
marmottajax.post({
    url: "post.php",
    options: { marmotte: "Dimou" }
});
```
post.php :
```php
<?php echo $_POST["marmotte"];
```

Toutes les options
----

```javascript
marmottajax.get({ // OU marmottajax.post() OU marmottajax()

    url: "", // obligatoire, peut être abrégé en marmottajax.get(url).then(callback); (voir premier exemple)

    method: "", // GET par defaut ou défini par marmottajax.get et marmottajax.post

    json: false, // false par defaut, la reponse sera automatiquement parsé si "true"

    options: {} // options à envoyer en GET (par l'url) ou en POST (dépend de la méthode)

}).then(function(result) {

    // result

}).error(function(message) {

    // message: "404", "invalid json" ou "unknow"

});
```

License
----

[WTFPL](http://www.wtfpl.net/)