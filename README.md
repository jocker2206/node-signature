# Firmador de PDF con node.js y Java


#### requerimientos 

```

 jdk8
 node.js 10.*

```


#### Configurar Hoja Cliente

```
    A0 => 2387 x 3370 (72pt)
    A1 => 1684 x 2384 (72pt)
    A2 => 1191 x 1684 (72)
    A3 => 842 x 1191 (72pt)
    A4 => 595 x 842 (72pt)
    ...
    
```


#### Medidas del rectagulo de la firma visible

```
    Width = 150
    Height = 70

```


#### Posiciones de la firma visible
las posiciones del rectangulo enpienza en 0

```
    A0 => 0 - 2287
    A1 => 0 - 1094
    A2 => 0 - 560
    A3 => 0 - 253
    A4 => 0 - 124
    ...
```


### ejemplo


```js

const Signer = require('./Signer');
const path = require('path');
const fs = require('fs');

let pfx = path.join(__dirname, "apples.pfx");
let pdf = path.join(__dirname, "example.pdf");
let salida = path.join(__dirname, "signature_example.pdf");

Signer(pfx, "apples", pdf, salida)
    .then(res => console.log(res))
    .catch(err => console.log(err));

```


```
#Output Success => {
    realPath: <ruta real pdf salida>
    message: "El pdf se firmó correctamente!"
} 

#Outout Error => Error: <message>
```