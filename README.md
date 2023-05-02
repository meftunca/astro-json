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
- HASHED -> parametre olarak formatını alır (md5,sha1...)
- Ref -> harici dosya için referans. Ek olarak pointer ile block seçilebilir
- Poly -> Polygon type
- Multi-Poly -> Multiple Polygons
- Point -> Point Type
- Multi-Point -> Multiple Point
- Line -> line
-> Multiple-Line -> Multiple Line
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

### Destek Listesi
- CRC (Cyclic Redundancy Check)
- MD5 (Message-Digest Algorithm 5)
- SHA-1 (Secure Hash Algorithm 1)
- SHA-2 (Secure Hash Algorithm 2)
- SHA-3 (Secure Hash Algorithm 3)
- BLAKE2 (optimized for 64-bit platforms)
- MurmurHash
- CityHash
- xxHash
- SipHash

```json
{
    "password": $HASHED("Hello, World","md5")
}
```

## Ref
```json
{
    "userName": $Ref("./person","4.name") // ./person dosyasından 4. elemanın name değerini alır
}
```

## Poly 
> En az 3 noktaya sahip vektörel değer
```json
{
    "poly": $Poly([
        [1,2],
        [3,4],
        [5,6]
    ]),
        "multiPoly": $Poly([
        [1,2],
        [3,4],
        [5,6]
    ],[
        [1,2],
        [3,4],
        [5,6]
    ]...),
}
```

## Point
```json
{
    "point": $Point(1,2),
    "multiPoint",$Point([1,2],[2,3])
}
```
## Line 
> En az 2 pointe sahip olan vektörel değer
```json
{
    "line": $Line([[1,2],[[1,2],[2,3]]]), // en az 2 point olarak 1 elemana sahiptir
    "multiPoint",$Point([[1,2],[[1,2],[2,3]]],[[1,2],[[1,2],[2,3]]]) // en az 2 line formatında elemana sahiptir
}
```
## Date
```json
{
    "date": $Date("2020-01-01 12:00:00",tz=+3)
}
```
