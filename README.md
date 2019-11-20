# **:triangular_flag_on_post: ANIMEFLV** (version 1.0.2)

![node version](https://img.shields.io/badge/node->=10.16.x-brightgreen.svg)
![npm version](https://img.shields.io/badge/npm->=6.9.x-brightgreen.svg)
          <a href="https://github.com/ChrisMichaelPerezSantiago/animefly/graphs/commit-activity">
            <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" target="_blank" />
          </a>
          <a href="https://github.com/ChrisMichaelPerezSantiago/animefly/blob/master/LICENSE">
            <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" target="_blank" />
          </a>
          <img src="https://img.shields.io/badge/now.sh-deployed-brightgreen.svg" alt="">
          <img src="https://badgen.net/badge/icon/now?icon=now&label" alt="">
          <img src="https://img.shields.io/badge/animeflv-API-brightgreen.svg" alt="">
          <img src="https://img.shields.io/github/stars/ChrisMichaelPerezSantiago/animeflv?style=social" alt="">
         


 <a href="https://nodei.co/npm/animeflv/"><img src="https://nodei.co/npm/animeflv.png"></a>


> This API will give you access to the content of the animeflv page. And you can enjoy all the chapters with sub in Spanish.

---

## *Please, do not download version v1.0.0 from npm, I had made the mistake of leaving the parameters in the functions with predefined values.* ️️️️❗️️️

## :rocket: Custom Animeflv API Link
[Animeflv API](https://animeflv.chrismichael.now.sh/api/v1/)

## **:package: Main tools used**

- [x] axios
- [x] body-parser
- [x] cheerio
- [x] compose-middleware
- [x] cors
- [x] dotenv
- [x] express
- [x] helmet
- [x] morgan
- [x] node-fetch

---

## **:wrench: Developer usage**

### **Set up project**

Before cloning the repo **be sure** you have installed:

- [**NODE**](https://www.google.com/search?q=how+to+install+node) (version >= 10.16.x)
- [**NPM**](https://www.google.com/search?q=how+to+install+npm) (version >= 6.9.x)

Then:

- Choose a folder project in your system and switch in `cd [folder path]`
- Clone the repo in your folder path `git clone https://github.com/ChrisMichaelPerezSantiago/animeflv.git`

---

### **Installation**

In order to install the project and all dependencies, enter in the project folder and run `npm install`

---

### Start the project

```bash
npm start
```

### Test the project

```bash
npm test
```

---


## API Documentation
### 📣Read this please | To get the videos!📣
## getAnimeServers([id])

*First of all I must mention that the url of the videos work only using the iframe element.*
*To get the videos (servers) of each chapter, you only need to use the getAnimeServers function that receives the id of the episode as a parameter.* 
*To verify the id of each episode, look at the episodes property:*

```json
"episodes": {
  "1": {
    "episode": 1,
    "id": "53099/psychopass-3-1"
  },
  "nextEpisodeDate": "2019-10-31"
}
```

*You just have to pass the id of the episode*
```javascript
getAnimeServers('53099/psychopass-3-1').then(doc => { console.log(doc) });
```

**output**
```javascript
[ 
  { server: 'm3u8',
    title: 'Streamium',
    allow_mobile: true,
    code:
     'https://streamium.xyz/embed.php?hash=6a2e46c779a8fc2b558ad3eed8c8b71a' },
  { server: 'natsuki',
    title: 'Natsuki',
    allow_mobile: true,
    code:
     'https://s1.animeflv.net/embed.php?s=natsuki&v=RmJwQlJnZ2FTVnhEVUlWQlFaVTI4bGtZeDl5SWNGSi81VXVvampCbExiUWJ2M2VxbnhoOENVclNyTzlnMEY4elppYi9oN2tFU3h5V25FUjJYZkR5bUVzNUpjVU52Um9jckRzNWttTDVuN0hkMm1ZWkNXNGlkakFiNEtpdC8rYm8=' },
  { server: 'vs',
    title: 'Verystream',
    allow_mobile: true,
    code: 'https://verystream.com/e/jJxesD2YJeb/' },
  { server: 'fembed',
    title: 'Fembed',
    allow_mobile: true,
    code: 'https://www.fembed.com/v/py13gum5eq77dwe' },
  { server: 'mega',
    title: 'MEGA',
    url:
     'https://mega.nz/#!6bABAAiA!WSJbevmfuOAJqgOom1ypYb85Ir95Z9aG2xwQUFHv1RI',
    allow_mobile: true,
    code:
     'https://mega.nz/embed#!6bABAAiA!WSJbevmfuOAJqgOom1ypYb85Ir95Z9aG2xwQUFHv1RI' },
  { server: 'streamango',
    title: 'Mango',
    url: 'https://streamango.com/f/mqpemtfrmortdqlt/',
    allow_mobile: true,
    code: 'https://streamango.com/embed/mqpemtfrmortdqlt' },
  { server: 'okru',
    title: 'Okru',
    allow_mobile: true,
    code: 'https://ok.ru/videoembed/1531214301706' },
  { server: 'yu',
    title: 'YourUpload',
    allow_mobile: true,
    code: 'https://www.yourupload.com/embed/V3e21a2MFF4H' },
  { server: 'maru',
    title: 'Maru',
    allow_mobile: true,
    code:
     'https://my.mail.ru/video/embed/8995617145282894610#budyak.rus#6930' },
  { server: 'netu',
    title: 'Netu',
    allow_mobile: true,
    code:
     'https://hqq.tv/player/embed_player.php?vid=MW9SaW94TnNpMm4rb3cyWnhsNDV4dz09' } 
]
```

*Now you just need to use the code property of each server and pass it to the **iframe***
```html
<iframe 
  src="https://streamium.xyz/embed.php?hash=6a2e46c779a8fc2b558ad3eed8c8b71a"
   width="100%"  
   height="100%" 
   frameborder="0" 
   allowfullscreen>
</iframe>
```
<iframe 
  src="https://streamium.xyz/embed.php?hash=6a2e46c779a8fc2b558ad3eed8c8b71a"
   width="100%"  
   height="100%" 
   frameborder="0" 
   allowfullscreen>
</iframe>


## search([query])
```javascript
// 20191030231015
// http://localhost:5000/api/v1/Search/tokyo%20ghoul

{
  "search": [
    {
      "title": "Tokyo Ghoul: Jack",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/2285.jpg",
      "synopsis": "OVA 4.5En Tokyo Ghoul: Jack, seguimos un incidente relacionado con un Ghoul devorador de humanos en el Distrito 13 de Tokio. Para descubrir la verdad de lo ocurrido a su amigo, el estudiante de instituto Taishi Fura persigue al Ghoul conocido como Lantern acompañado del joven investigador Kisho Arima. La historia cuenta cómo Arima y Fura se ...",
      "debut": null,
      "type": "OVA",
      "rating": "4.5",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "37923/tokyo-ghoul-jack-1"
        },
        "nextEpisodeDate": null
      }
    },
    {
      "title": "Tokyo Ghoul",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/1415.jpg",
      "synopsis": "Anime 4.5Extraños asesinatos se están sucediendo uno tras otro en Tokyo. Debido a las pruebas encontradas en las escenas, la policía concluye que los ataques son obra de ghouls que se comen a las personas. Kaneki y Hide, dos compañeros de clase, llegan a la conclusión de que si nadie ha visto nunca a esos necrófagos...",
      "debut": null,
      "type": "Anime",
      "rating": "4.5",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "26103/tokyo-ghoul-1"
        },
        "2": {
          "episode": 2,
          "id": "26188/tokyo-ghoul-2"
        },
        "3": {
          "episode": 3,
          "id": "26278/tokyo-ghoul-3"
        },
        "4": {
          "episode": 4,
          "id": "26373/tokyo-ghoul-4"
        },
        "5": {
          "episode": 5,
          "id": "26431/tokyo-ghoul-5"
        },
        "6": {
          "episode": 6,
          "id": "26529/tokyo-ghoul-6"
        },
        "7": {
          "episode": 7,
          "id": "26689/tokyo-ghoul-7"
        },
        "8": {
          "episode": 8,
          "id": "27092/tokyo-ghoul-8"
        },
        "9": {
          "episode": 9,
          "id": "27741/tokyo-ghoul-9"
        },
        "10": {
          "episode": 10,
          "id": "28001/tokyo-ghoul-10"
        },
        "11": {
          "episode": 11,
          "id": "28459/tokyo-ghoul-11"
        },
        "12": {
          "episode": 12,
          "id": "28800/tokyo-ghoul-12"
        },
        "nextEpisodeDate": null
      }
    },
  ]
}
```

## latestAnimeAdded()
*It will show N data per page , Total page unknown.*

```javascript
// 20191030104518
// http://localhost:5000/api/v1/LatestAnimeAdded

{
  "animes": [
    {
      "title": "Psycho-Pass 3",
      "poster": "https://animeflv.net/uploads/animes/covers/3225.jpg",
      "synopsis": "Anime 4.8En un futuro próximo, es posible medir de forma instantánea el estado mental de una persona, la personalidad y la probabilidad de que dicha persona vaya a cometer delitos gracias a un escáner psico-somático que realiza un escaneo de las funciones del cerebro y demás funciones biológicas y quí...",
      "debut": "estreno",
      "type": "Anime",
      "rating": "4.8",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53099/psychopass-3-1"
        },
        "nextEpisodeDate": "2019-10-31"
      }
    },
    {
      "title": "Chihayafuru 3",
      "poster": "https://animeflv.net/uploads/animes/covers/3224.jpg",
      "synopsis": "Anime 4.4Tercera temporada.",
      "debut": "estreno",
      "type": "Anime",
      "rating": "4.4",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53082/chihayafuru-3-1"
        },
        "2": {
          "episode": 2,
          "id": "53135/chihayafuru-3-2"
        },
        "3": {
          "episode": 3,
          "id": "53136/chihayafuru-3-3"
        },
        "nextEpisodeDate": "2019-11-05"
      }
    },
  ]
}
```

## latestEpisodesAdded()
*It will show N data per page , Total page unknown.*

```javascript
// 20191030104703
// http://localhost:5000/api/v1/LatestEpisodesAdded

{
  "episodes": [
    {
      "title": "Radiant 2nd Season",
      "poster": "https://animeflv.net/uploads/animes/thumbs/3184.jpg",
      "episode": 5,
      "servers": [
        {
          "server": "m3u8",
          "title": "Streamium",
          "allow_mobile": true,
          "code": "https://streamium.xyz/embed.php?hash=aac84b2086a995b9bc83fb8eb2d627d9"
        },
        {
          "server": "natsuki",
          "title": "Natsuki",
          "allow_mobile": true,
          "code": "https://s1.animeflv.net/embed.php?s=natsuki&v=TU1Sc0FHRW1CelV6U3FsaDdiYkU0OEpVNUFndDBnYnhCRDRCTFpDTDFVNlFjc0JGcTdrWlM1aFRObXdWd3RoK1VRdUdpT2J3QXlUK0R3Wm94dU1mbHhvN0lsU1BKc3FHbUsycHpQa0pOQUJJbDQ3YmxKdXdvSEFkc2Y4MklxMW96bUdJd2k3aEZBWDFDQzNyYXd0WnZ3PT0="
        },
        {
          "server": "vs",
          "title": "Verystream",
          "allow_mobile": true,
          "code": "https://verystream.com/e/KxLfdtqQGtY/"
        },
        {
          "server": "fembed",
          "title": "Fembed",
          "allow_mobile": true,
          "code": "https://www.fembed.com/v/-z85qtpmljp2j0n"
        },
        {
          "server": "mega",
          "title": "MEGA",
          "url": "https://mega.nz/#!eeREmQDR!35kX8v-mJe0vzW-C4seMvQ1rPGqttj6anYneFOz0m6g",
          "allow_mobile": true,
          "code": "https://mega.nz/embed#!eeREmQDR!35kX8v-mJe0vzW-C4seMvQ1rPGqttj6anYneFOz0m6g"
        },
        {
          "server": "okru",
          "title": "Okru",
          "allow_mobile": true,
          "code": "https://ok.ru/videoembed/1723453344498"
        },
        {
          "server": "yu",
          "title": "YourUpload",
          "allow_mobile": true,
          "code": "https://www.yourupload.com/embed/34qV7t4n2jqk"
        },
        {
          "server": "maru",
          "title": "Maru",
          "allow_mobile": true,
          "code": "https://my.mail.ru/video/embed/8995617145282894650#budyak.rus#6970"
        }
      ]
    },
  ]
}
```

## animeByGenres([genre], [sortBy] , [page])

<table>
<tr><th>Genres</th><th>SortBy</th><th>Page</th></tr>
<tr><td>

|   genres            |                        |                 |
|---------------------|------------------------|-----------------|
|accion               |  infantil              | sobrenatural    |
|artes-marciales      |  josei                 | superpoderes    |
|aventura             |  juegos                | suspenso        |
|carreras             |  magia                 | terror          |
|ciencia-ficcion      |  mecha                 | vampiros        |
|comedia              |  militar               | yaoi            |
|demencia             |  misterio              | yuri            |
|demonios             |  musica                |                 |
|deportes             |  parodia               |                 |
|drama                |  psicologico           |                 |
|ecchi                |  recuentos-de-la-vida  |                 |
|escolares            |  romance               |                 |
|espacial             |  samurai               |                 |
|fantasia             |  seinen                |                 |
|harem                |  shoujo                |                 |
|historico            |  shounen               |                 |

</td><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|
</table>


```javascript
// 20191030121938
// http://localhost:5000/api/v1/Genres/accion/updated/1

{
  "animes": [
    {
      "title": "Psycho-Pass 3",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3225.jpg",
      "synopsis": "Anime 0.0En un futuro próximo, es posible medir de forma instantánea el estado mental de una persona, la personalidad y la probabilidad de que dicha persona vaya a cometer delitos gracias a un escáner psico-somático que realiza un escaneo de las funciones del cerebro y demás funciones biológicas y químicas del cuerpo, determinando el Psycho-Pass, un ...",
      "debut": null,
      "type": "Anime",
      "rating": "0.0",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53099/psychopass-3-1"
        },
        "nextEpisodeDate": "2019-10-31"
      }
    },
    {
      "title": "Ginga Eiyuu Densetsu: Die Neue These - Seiran 1",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3223.jpg",
      "synopsis": "Película 0.0El estancamiento de 150 años entre las dos superpotencias interestelares, el Imperio Galáctico y la Alianza de Planetas Libres, llega a su fin cuando surge una nueva generación de líderes: el genio militar idealista Reinhard von Lohengramm, y el reservado historiador de la APL, Yang Wenli.\nMientras Reinhard sube a las filas del Imperio con l...",
      "debut": null,
      "type": "Película",
      "rating": "0.0",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53046/ginga-eiyuu-densetsu-die-neue-these-seiran-1-1"
        },
        "2": {
          "episode": 2,
          "id": "53047/ginga-eiyuu-densetsu-die-neue-these-seiran-1-2"
        },
        "3": {
          "episode": 3,
          "id": "53048/ginga-eiyuu-densetsu-die-neue-these-seiran-1-3"
        },
        "4": {
          "episode": 4,
          "id": "53049/ginga-eiyuu-densetsu-die-neue-these-seiran-1-4"
        },
        "nextEpisodeDate": null
      }
    },
  ]
}
```

## movies([sortBy] , [page])
<table>
<tr><th>SortBy</th><th>Page</th></tr>
<tr><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|

</td></tr> </table>

```javascript
// 20191030124010
// http://localhost:5000/api/v1/Movies/rating/1

{
  "movies": [
    {
      "title": "Youjo Senki Movie",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3182.jpg",
      "synopsis": "Película 4.9Año 1926. El Batallón Aéreo de Magos 203 del Ejército Imperial, comandado por la Mayor Tanya von Degurechaff, se alzó con la victoria en la batalla del sur contra la República. Habiendo regresado bañados en gloria y con las mieles del éxito en la boca, esperaban poder descansar un poco, pero el cuartel general les envía nuevas órdenes esp...",
      "debut": null,
      "type": "Película",
      "rating": "4.9",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "52790/youjo-senki-movie-1"
        },
        "nextEpisodeDate": null
      }
    },
  ]
}
```

## ova([sortBy] , [page])
<table>
<tr><th>SortBy</th><th>Page</th></tr>
<tr><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|

</td></tr> </table>

```javascript
// 20191030125306
// http://localhost:5000/api/v1/Ova/default/1

{
  "ova": [
    {
      "title": "Gundam Build Divers Re:Rise",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3212.jpg",
      "synopsis": "OVA 0.0Segunda temporada de Gundam Build Divers",
      "debut": null,
      "type": "OVA",
      "rating": "0.0",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "52989/gundam-build-divers-rerise-1"
        },
        "2": {
          "episode": 2,
          "id": "52990/gundam-build-divers-rerise-2"
        },
        "3": {
          "episode": 3,
          "id": "53040/gundam-build-divers-rerise-3"
        },
        "4": {
          "episode": 4,
          "id": "53093/gundam-build-divers-rerise-4"
        },
        "nextEpisodeDate": "2019-10-31"
      }
    },
  ]
}
```

## special([sortBy] , [page])
<table>
<tr><th>SortBy</th><th>Page</th></tr>
<tr><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|

</td></tr> </table>

```javascript
// 20191030124909
// http://localhost:5000/api/v1/Special/added/1

{
  "special": [
    {
      "title": "Fate/Grand Order: Zettai Majuu Sensen Babylonia - Initium Iter",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3181.jpg",
      "synopsis": "Especial 4.6Año 2017. La última era en la que existió la magia. Los humanos crearon la sociedad, pero los Magos fueron quienes consiguieron alcanzar la verdad del mundo. La magia se compone de técnicas del pasado que la ciencia no puede explicar, mientras que la ciencia se compone de técnicas del futuro que la magia no puede alcanzar. Estudiosos e investi...",
      "debut": null,
      "type": "Especial",
      "rating": "4.6",
      "episodes": {
        "0": {
          "episode": 0,
          "id": "52745/fategrand-order-zettai-majuu-sensen-babylonia-initium-iter-0"
        },
        "nextEpisodeDate": null
      }
    },
  ]
}
```


## tv([sortBy] , [page])
<table>
<tr><th>SortBy</th><th>Page</th></tr>
<tr><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|

</td></tr> </table>

```javascript
// 20191030125732
// http://localhost:5000/api/v1/TV/default/1

{
  "tv": [
    {
      "title": "Psycho-Pass 3",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3225.jpg",
      "synopsis": "Anime 0.0En un futuro próximo, es posible medir de forma instantánea el estado mental de una persona, la personalidad y la probabilidad de que dicha persona vaya a cometer delitos gracias a un escáner psico-somático que realiza un escaneo de las funciones del cerebro y demás funciones biológicas y químicas del cuerpo, determinando el Psycho-Pass, un ...",
      "debut": null,
      "type": "Anime",
      "rating": "0.0",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53099/psychopass-3-1"
        },
        "nextEpisodeDate": "2019-10-31"
      }
    },
  ]
}
```


## animeByState([state] , [sortBy] , [page])
<table>
<tr><th>Status</th><th>SortBy</th><th>Page</th></tr>
<tr><td>

|  state       |  value  |
|--------------|---------|
|  In emission |   1     |
|  Finalized   |   2     |
|  coming soon |   3     |

</td><td>

| sortBy                 |  value   |
|----------------------- |----------|
| default anime order    | default  |
| Recently Updated anime | updated  |
| Recently Added anime   | added    |
| anime by Rating        | rating   |
| anime by Title         | title    |

</td><td>

| pages  |
|--------|
| [1 .. total page unknown]|

</td></tr> </table>

### In Emission [state = 1]
```javascript
// 20191030132847
// http://localhost:5000/api/v1/AnimeByState/1/default/1

{
  "animes": [
    {
      "title": "Psycho-Pass 3",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3225.jpg",
      "synopsis": "Anime 0.0En un futuro próximo, es posible medir de forma instantánea el estado mental de una persona, la personalidad y la probabilidad de que dicha persona vaya a cometer delitos gracias a un escáner psico-somático que realiza un escaneo de las funciones del cerebro y demás funciones biológicas y químicas del cuerpo, determinando el Psycho-Pass, un ...",
      "debut": null,
      "type": "Anime",
      "rating": "0.0",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "53099/psychopass-3-1"
        },
        "nextEpisodeDate": "2019-10-31"
      }
    },
  ]
}
```

### Finalized [state = 2]

```javascript
// 20191030132916
// http://localhost:5000/api/v1/AnimeByState/2/default/1

{
  "animes": [
    {
      "title": "Try Knights",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/3180.jpg",
      "synopsis": "Anime 2.9Akira, el nuevo miembro del club de rugby, recibe el consejo de que no se acerque mucho a Riku, quien es un fanático del rugby pero lo abandonó porque no tenía el físico necesario para practirarlo. A pesar de ello, Akira se interesa por Riku y la pasión por el rugby de este regresa gradualmente. Al unir fuerzas, la pareja consigue practicar un...",
      "debut": null,
      "type": "Anime",
      "rating": "2.9",
      "episodes": {
        "1": {
          "episode": 1,
          "id": "52498/try-knights-1"
        },
        "2": {
          "episode": 2,
          "id": "52546/try-knights-2"
        },
        "3": {
          "episode": 3,
          "id": "52591/try-knights-3"
        },
        "4": {
          "episode": 4,
          "id": "52637/try-knights-4"
        },
        "5": {
          "episode": 5,
          "id": "52687/try-knights-5"
        },
        "6": {
          "episode": 6,
          "id": "52734/try-knights-6"
        },
        "7": {
          "episode": 7,
          "id": "52780/try-knights-7"
        },
        "8": {
          "episode": 8,
          "id": "52826/try-knights-8"
        },
        "9": {
          "episode": 9,
          "id": "52902/try-knights-9"
        },
        "10": {
          "episode": 10,
          "id": "52929/try-knights-10"
        },
        "11": {
          "episode": 11,
          "id": "52977/try-knights-11"
        },
        "12": {
          "episode": 12,
          "id": "53030/try-knights-12"
        },
        "nextEpisodeDate": null
      }
    },
  ]
}
```

### Coming Soon [state = 3]
```javascript
// 20191030133002
// http://localhost:5000/api/v1/AnimeByState/3/default/1

{
  "animes": [
    {
      "title": "Ame-iro Cocoa in Hawaii",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/2559.jpg",
      "synopsis": "Anime 4.2¡¿El Cafe Rainy Color se está expandiendo a Hawaii!?\nDe repente un día Nozomu Tokura se designa el gerente de la tienda por orden del propietario. Desconcertado, sin embargo, con la cooperación de todos y el apoyo de nuevos amigos locales, Nozomu ahora tiene una batalla cuesta arriba para abrir la nueva tienda. &i...",
      "debut": null,
      "type": "Anime",
      "rating": "4.2",
      "episodes": {
        "nextEpisodeDate": null
      }
    },
    {
      "title": "Mahou Shoujo? Naria☆Girls",
      "poster": "https://animeflv.nethttps://animeflv.net/uploads/animes/covers/2506.jpg",
      "synopsis": "Anime 4.3La historia gira en torno a unas chicas llamadas Urara, Hanabi y Inaho, que aspiran a alcanzar la fama en todo Japón haciendo versiones anime de ellas mismas. Para atraer a todo el mundo, desde pequeños a adultos, deciden que el género sea magical girls. Ahora tienen como objetivo emitir una temporada de anime.",
      "debut": null,
      "type": "Anime",
      "rating": "4.3",
      "episodes": {
        "nextEpisodeDate": null
      }
    },
  ]
}
```

## **:handshake: Contributing**

- Fork it!
- Create your feature branch: `git checkout -b my-new-feature`
- Commit your changes: `git commit -am 'Add some feature'`
- Push to the branch: `git push origin my-new-feature`
- Submit a pull request

---

### **:busts_in_silhouette: Credits**

- [Chris Michael](https://github.com/ChrisMichaelPerezSantiago) (Project Leader, and Developer)

---

### **:anger: Troubleshootings**

This is just a personal project created for study / demonstration purpose and to simplify my working life, it may or may
not be a good fit for your project(s).

---

### **:heart: Show your support**

Please :star: this repository if you like it or this project helped you!\
Feel free to open issues or submit pull-requests to help me improving my work.


---

### **:robot: Author**

_*Chris Michael*_

> You can follow me on
[github](https://github.com/ChrisMichaelPerezSantiago)&nbsp;&middot;&nbsp;[twitter](https://twitter.com/Chris5855M)

---

Copyright © 2019 [Chris Michael](http://personal-porfolio.chrismichael.now.sh).
