# astro-json
C++ Dom Manipulator

# Desteklenen Veri Türleri
- String
- Number
- Null
- Boolean
- Object
- Array


# Desteklenecek veri türleri
- ID -> uuid,big integer ve object id parametrelerini alabilir
- HASHED -> parametre olarak formatını alır
- Ref -> harici dosya için referans. Ek olarak pointer ile block seçilebilir
- Poly -> Polygon type
- Point -> Point Type
- Date -> Tarih ve saat formatı

# Örnekler
## String
```json
{
    "name": "string"
}
```

## Number
```json
{
    "age": 32
}
```

## Null
```json
{
    "null": null
}
```

## Boolean
```json
{
    "isTrue": true
}
```

## Object
```json
{
    "person": {
        "name": "string",
        "age": 32
    }
}
```

## Array
```json
{
    "persons": [
        {
            "name": "string",
            "age": 32
        }
    ]
}
```

## ID
```json
{
    "id": $ID(uuid),
    "id2": $ID(bigint),
    "id3": $ID(objectid)
}
```

## HASHED
```json
{
    "password": $HASHED(md5)
}
```

## Ref
```json
{
    "userName": $Ref("./person","4.name") // ./person dosyasından 4. elemanın name değerini alır
}
```

## Poly
```json
{
    "poly": $Poly([
        [1,2],
        [3,4],
        [5,6]
    ])
}
```

## Point
```json
{
    "point": $Point(1,2)
}
```

## Date
```json
{
    "date": $Date("2020-01-01 12:00:00",tz=+3)
}
```
