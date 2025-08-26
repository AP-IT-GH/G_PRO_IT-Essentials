# Bits & Bytes
Zoals daarnet reeds aangehaald werd maken computers gebruik van het binaire talstelel om gegevens te verwerken, waaronder letters, cijfers en symbolen. Om character encoding goed te begrijpen, moeten we daarom eerst weten wat bits en bytes zijn en hoe ze zich verhouden tot het binaire talstelsel.

## Wat is een bit?
Een bit is de kleinste eenheid van digitale informatie en kan twee waarden hebben:

* 0 (uit)
* 1 (aan)

Computers gebruiken bits om alles op te slaan en te verwerken, inclusief tekst, afbeeldingen en geluid.

## Wat is een byte?
Een byte bestaat uit 8 bits en kan 256 verschillende waarden aannemen ($2^8$ = 256).

| Bits     | Decimale waarde |
|----------|-----------------|
| 00000000 | 0               |
| 00000001 | 1               |
| 00000010 | 2               |
| ...      | ...             |
| 11111111 | 255             |

**💡 Waarom 8 bits?**
Omdat een byte precies genoeg ruimte biedt voor ASCII-karakters (0-127 past in 7 bits, maar we gebruiken meestal 8 bits).

**Voorbeeld:**
De letter A in ASCII wordt opgeslagen als 01000001 (65 in decimaal). De spatie ( ) is 00100000 (32 in decimaal).


## Hoe verhouden bits en bytes zich tot elkaar?
| Eenheid         | Grootte                           |
|-----------------|-----------------------------------|
| 1 bit           | 0 of 1                            |
| 1 byte          | 8 bits                            |
| 1 kilobyte (KB) | 1024 bytes                        |
| 1 megabyte (MB) | 1024 KB (1.048.576 bytes)         |
| 1 gigabyte (GB) | 1024 MB (1.073.741.824 bytes)     |
| 1 terabyte (TB) | 1024 GB (1.099.511.627.776 bytes) |

**Waarom 1024 en niet 1000?**
Omdat computers werken met binaire machten van 2, en 1024 is $2^{10}$.

## Waarom is dit relevant voor character encoding?
Omdat verschillende encodings een verschillend aantal bits en bytes per karakter gebruiken:

| Encoding       | Bits per karakter                | Opslagruimte |
|----------------|----------------------------------|--------------|
| ASCII          | 7 bits (gebruikt meestal 8 bits) | 1 byte       |
| Extended ASCII | 8 bits                           | 1 byte       |
| UTF-8          | 8-32 bits                        | 1-4 bytes    |
| UTF-16         | 16-32 bits                       | 2-4 bytes    |
| UTF-32         | 32 bits                          | 4 bytes      |

