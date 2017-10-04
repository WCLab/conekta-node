# Conekta NodeJS Promises

Conekta Node v 3.2.0
======================
Exactly the same package as [conekta-node](https://www.npmjs.com/package/conekta) but this one uses promises instead of callbacks
Wrapper to connect with https://api.conekta.io.

## Install

```sh
npm i conekta-promises -S
```

## Usage with Promises

```node
var conekta = require('conekta-promises');

conekta.api_key = '9YxqfRnx4sMQDnRsqdYn';
conekta.locale = 'es';

conekta.Order.create({
    "currency": "MXN",
    "customer_info": {
        "name": "Jul Ceballos",
        "phone": "+5215555555555",
        "email": "jul@conekta.io"
    },
    "line_items": [{
        "name": "Box of Cohiba S1s",
        "description": "Imported From Mex.",
        "unit_price": 35000,
        "quantity": 1,
        "tags": ["food", "mexican food"],
        "type": "physical"
    }]
}).then(function(res){
  console.log(res.toObject());
}).catch(function(err){
  console.log(err.type);
});
```
## Async and Await (Node v8 required)

```node
const conekta = require('conekta');

conekta.api_key = '9YxqfRnx4sMQDnRsqdYn';
conekta.locale = 'es';

try {
    let order = await conekta.Order.create({
        "currency": "MXN",
        "customer_info": {
            "name": "Jul Ceballos",
            "phone": "+5215555555555",
            "email": "jul@conekta.io"
        },
        "line_items": [{
            "name": "Box of Cohiba S1s",
            "description": "Imported From Mex.",
            "unit_price": 35000,
            "quantity": 1,
            "tags": ["food", "mexican food"],
            "type": "physical"
        }]
    });

    console.log(res.toObject());
} catch (error) {
    console.log(err.type);
}
```

## Endpoints

```node
Conekta.Order.create
Conekta.Order.update
Conekta.Order.find
Conekta.Order.where
Conekta.Order.createCharge
Conekta.Order.createLineItem
Conekta.Lineitem.update
Conekta.Order.createTaxLine
Conekta.TaxLine.update
Conekta.Order.createShippingLine
Conekta.ShippingLine.update
Conekta.Order.createDiscountLine
Conekta.DiscountLine.update
Conekta.Customer.create
Conekta.Customer.update
Conekta.Customer.find
Conekta.Customer.where
Conekta.Customer.destroy
Conekta.Customer.createSource
Conekta.Source.update
Conekta.Customer.createShippingContact
Conekta.ShippingContact.update
Conekta.Customer.createFiscalEntity
Conekta.FiscalEntity.update
```

## Documentation

Please see https://developers.conekta.com/api for up-to-date documentation.

## Contribute

### Clone repo

```sh
$ git clone https://github.com/crashingalexsan/conekta-node
$ cd conekta-node
```

### Install dependencies

```sh
$ npm install
```

### Run interactive mode

```sh
$ bin/console
Welcome to Conekta node console!
Help: exit() to quit

> conekta.api_key = '9YxqfRnx4sMQDnRsqdYn';
'9YxqfRnx4sMQDnRsqdYn'
> conekta.locale = 'es';
'es'
>
```

## Send pull requests

We love pull requests, send them from your fork to branch **master** into **crashingalexsan/conekta-node**

## License

Developed in Mexico by [Conekta](https://www.conekta.com). Available with [MIT License](LICENSE).


