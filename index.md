
Tämä artikkeli on osa sarjaa, jossa tutustutaan funktionaaliseen ohjelmointiin javascriptillä. 

### Esitiedot

Javascript (ES16) sekä ...

### Setup

```
yarn add ramda
```
tai
```
npm install ramda
```

### Ramda

Artikkelissa käytetään kirjastoa [**Ramda**](https://ramdajs.com/). Ramda kertoo tärkeimpien ominaisuuksiensa olevan:
- Puhtaat funktiot (**Pure functions**)
- Kaikki funktiot curriattu (**Curry**)
- Funktioiden parametrit on järjestetty siten, että data tulee aina viimeisenä (**Data last**)

Tämän artikkelin tavoitteena on auttaa ymmärtämään miksi edelle esitetyt ominaisuudet ovat hyödyllisiä. 

### Funktiot

Esim.
```
function sum (x, y) {
  return x + y
}

const sum = (x, y) => x + y
```

### Termeistä

Tässä määritellään muutama artikkelissa käytetty termi. 

#### Konteksti

Konteksti on javascriptissä tärkeä käsite. 
```
this
```

### Puhtaat Funktiot

Ovat funktioita, jotka eivät aiheuta minkäänlaisia sivuvaikutuksia oman kontekstinsa ulkopuolelle. Puhtailla funktioilla on vain **input** ja **output**.

puhdas
```
const square = x => x * x
```
epäpuhdas
```
let count = 0
const add1 = () => count++
```
Puhtaat funktiot varmistavat ettei muuttujia voi muokata niiden kontekstin ulkopuolella. Aina kun halutaan erilainen muuttuja alkuperäisestä, syötetään se funktioon ja funktio palauttaa uuden muuttujan.

### Javascriptin valmis funktionaalinen tuki
```
const nums = [1, 2, 3]
const square = x => x * x
const isEven = x => x % 2 === 0
```
Javascript
```
nums.map(square) // -> [1, 4, 9]
nums.filter(isEven) // -> [2]
```

Ramda
```
import { map, filter } from 'ramda'

map(square, nums) // -> [1, 4, 9]
filter(isEven, nums) // -> [2]
```
### Kompositiot

Funktioita voi yhdistää.

```
import { compose } from 'ramda'

const alter = (array) => compose(
  filter(isEven, array),
  map(square, array)
) 

alter(nums)
// -> [4]
```

### Curry

Funktiot voivat palauttaa funktioita.

### Argumenttien järjestys

Kuten todettiin, yksi Ramdan keskeisiä suunnitteluperiaatteita on “data viimeisenä”.
 




## OSA 2
### Pointfree

Data viimeisenä, Curry

### Lenses


## OSA 3
### Kategoriateoria
