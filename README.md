# Simulateur de résultats d'élections

Ce simulateur calcule la distribution des sièges au conseil communal sur base du nombre de voix accordées à chaque liste.
En Belgique, le calcul se fait sur base de la clé Imperiali, soit les X meilleurs quotients successifs du scrutin (en commençant par /2 jusque /X -la clé d'Hondt commence par /1), où X est le nombre de sièges à attribuer .

## Ajouter ma commune

Malheureusement, à l'heure où j'écris ce texte, je n'ai pas eu le temps de trouver une source de données facilement exploitable me permettant de récupérer les résultats de 2012 pour comparaison, ni les listes en présence en 2018.
**Si vous le souhaitez, vous pouvez m'envoyer les données de votre commune** soit via pull request, soit par mail à jmleroy@gmail.com. Je tâcherai de les intégrer aussitôt que possible. Vous trouverez ci-dessous la structure des données à m'envoyer.

## Structure des données communales

Le texte après `//` est un commentaire pour votre compréhension, il ne devra pas m'être envoyé.

Une liste de noms de couleurs peut être trouvée à https://en.wikipedia.org/wiki/Web_colors .

```json
	"Nom de votre commune": {
        maxVotes: 3904, // Nombre d'électeurs en 2018
        maxSeats: 17, // Nombre de sièges en 2018
        previousMaxVotes: 3731, // Nombre d'électeurs en 2012
        previousMaxSeats: 15, // Nombre de sièges en 2012
        lists: {
            "Nom de la liste 1": {
                backgroundColor: "#3AAA11", // Couleur de fond (ici, en hexadécimal) 
                textColor: "White", // Couleur de texte
                previousName: "Nom de cette liste en 2012", // (facultatif)
                previousVotes: 410, // Nombre de voix en 2012 (facultatif)
                previousSeats: 1 // Nombre de sièges en 2012 (facultatif)
            },
            "Nom de Liste 2": {
                backgroundColor: "Yellow",
                textColor: "Black",
                previousName: "Nom précédent 2",
                previousVotes: 1443,
                previousSeats: 6
            }
        }
    }
```

## Licence

Ce script est placé sous licence [Creative Commons CC-BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr)
