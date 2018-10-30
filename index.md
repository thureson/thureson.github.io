
Tämä artikkeli on osa sarjaa, jossa tutustutaan funktionaaliseen ohjelmointiin javascriptillä. 

### Esitiedot

Javascript (ES16) sekä ...

### Setup

```
yarn add ramda
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

### Puhtaat Funktiot

Ovat funktioita, jotka eivät aiheuta minkäänlaisia sivuvaikutuksia oman kontekstinsa ulkopuolelle. Puhtailla funktioilla on vain **input** ja **output**.

puhdas
```
const sum = (x, y) => x + y
```
epäpuhdas
```
let count = 0
const add1 = () => count++
```
Puhtaat funktiot varmistavat ettei muuttujia voi muokata. Aina kun halutaan erilainen muuttuja alkuperäisestä, syötetään se funktioon ja funktio palauttaa uuden muuttujan.

### Javascriptin valmis funktionaalinen tuki
```
const nums = [true,true, false]
const reverse = x => !x 
```
Javascript
```
nums.map(reverse) // -> [false, false, true]
nums.filter(reverse) // -> [false]
```

Ramda
```
import { map, filter } from 'ramda'

map(reverse, nums) // -> [false, false, true]
filter(reverse, nums) // -> [false]
```
### Kompositiot

Funktioita voi yhdistää.

```
import { compose } from 'ramda'

const alter = (array) => compose(
  map(),
  filter()
)
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
