# Custom Name Generator
Extends the original package [project-name-generator](https://github.com/aceakash/project-name-generator) from [Akash Kurdekar](https://github.com/aceakash) by allowing custom adjectives and nouns.

Generate quirky names like *spiffy-waterfall*, *sassy-bread*, *mature-dew-8239* to use wherever you need a random but memorable name.

Useful for object names, temp folders, passwords, project names, unique ids etc

## Install
`npm install @good-ghosting/custom-name-generator --save`

## Quick Start
```javascript
var generate = require('@good-ghosting/custom-name-generator');

generate().dashed; // 'uptight-guitar'

generate().spaced; // 'grandiose clam'

generate().raw; // ['deluxe', 'grandmother']

generate({ number: true }).dashed; // 'disgraceful-temper-7794'

generate({ words: 4 }).raw; // ['tiny', 'crabby', 'wired', 'quicksand']

generate({ words: 3, adjectives: ['nice', 'warm', 'wired',], nouns: ['guitar', 'beach'] }).raw; // ['nice', 'wired', 'guitar']

generate({ words: 4, number: true }).dashed; // 'breakable-judicious-luxuriant-tax-3931'

generate({ words: 2, alliterative: true }).spaced; // 'elegant experience'

```


## API
The module returns a single function, `generate(options)`

Calling `generate()` with no arguments will return an object:
```javascript
{
    raw: ['whispering', 'valley'],
    dashed: 'whispering-valley',
    spaced: 'whispering valley'
}
```

The `options` argument object can have properties

* **words** (number) - Number of words generated (excluding number). All words will be adjectives, except the last one which will be a noun. Defaults to **2**.
* **number** (boolean) - Whether a numeric suffix is generated or not. The number is between 1 - 9999, both inclusive. Defaults to **false**.
* **alliterative** (boolean) - Whether to output words beginning with the same letter or not. Defaults to **false**.

`generate({ words: 3 })` will return:
```javascript
{
    raw: ['harmonious', 'endurable', 'substance'],
    dashed: 'harmonious-endurable-substance',
    spaced: 'harmonious endurable substance'
}
```

`generate({ words: 5, number: true })` will return:
```javascript
{
  raw: [ 'exciting', 'cooperative', 'legal', 'lackadaisical', 'blood', 4099 ],
  dashed: 'exciting-cooperative-legal-lackadaisical-blood-4099',
  spaced: 'exciting cooperative legal lackadaisical blood 4099'
}
```

`generate({ words: 2, number: false, alliterative: true })` will return:
```javascript
{
  raw: [ 'elegant', 'experience' ],
  dashed: 'elegant-experience',
  spaced: 'elegant experience'
}
```

## Tests
To run tests locally:
```
npm install
// run yarn install if preferred or have any issues with npm install

npm test
```

The library has been tested with Node.js 16.17.1
