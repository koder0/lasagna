# Lucian ínycsiklandó lasagnéja

Üdvözlünk a(z) Lucian ínycsiklandó lasagnéja feladatnál az Exercism PHP kurzusán.
Ha segítségre van szükséged a tesztek futtatásához vagy a kódod beküldéséhez, nézd meg a `HELP.md` fájlt.
Ha elakadsz a feladatnál, nézd meg a `HINTS.md` fájlt, de először próbáld meg azok nélkül megoldani :)

## Introduction

## Alapok

Ha részletesebb információra vágysz ezekről a témákról, látogasd meg a [fogalom oldalt][exercism-concept].

### Általános szintaxis

A `<?php` PHP nyitó tag jelzi a PHP-kód kezdetét.
Az utasítások elválasztásához minden utasítást `;`-vel kell lezárni.

```php
<?php

$message = "Success!"; // Statement correctly ends with `;`
$message = "I fail." // PHP Parse error: syntax error, [...]
```

A könnyebb olvashatóság érdekében a kódpéldákból hiányzik a `<?php` nyitó tag.

### Megjegyzések

Az egysoros megjegyzések `//`-vel kezdődnek.

```php
// Single line comment
```

### Értékek és változók

Az értékadó `=` operátorral értéket rendelhetsz egy változóhoz.
A változóneveknek dollárjellel (`$`) kell kezdődniük, és követniük kell a [névadási konvenciókat][exercism-concept-naming-conventions].

```php
$count = 1; // Assign value of 1

// Strings can be created by enclosing the characters
// within single `'` quotes or double `"` quotes.
$message = "Success!";
```

### Függvények és metódusok

Értékeket és változókat adhatsz át függvényeknek.
A függvény argumentumai új változókká válnak, amelyekben az átadott értékek tárolódnak.
A függvények a `return` kulcsszó használatával bármilyen értéket visszaadhatnak.

```php
function window_height($height)
{
    return $height + 10;
}

window_height(100);
// => 110
```

Az osztályokon belüli, illetve azok példányain lévő függvényeket metódusnak nevezzük.
Egy metódus meghívásához a neve elé a példányt és egy `->` jelet kell írni.
A metódusok hozzáférnek a speciális `$this` változóhoz, amely az aktuális példányra hivatkozik.

```php
<?php

class Calculator {
    public function sub($x, $y)
    {
        return $this->add($x, -$y); // Calls the method add() of the current instance
    }

    public function add($x, $y)
    {
        return $x + $y;
    }
}

$calculator = new Calculator(); // Creates a new instance of Calculator class
$calculator->sub(3, 1); // Calls the method sub() of the instance stored in $calculator
// => 2
```

[exercism-concept]: /tracks/php/concepts/basic-syntax
[exercism-concept-naming-conventions]: /tracks/php/concepts/basic-syntax#h-naming-conventions

## Instructions

Ebben a feladatban kódot írsz majd, hogy segíts elkészíteni egy remek lasagnét a kedvenc szakácskönyvedből.

Öt részfeladat vár rád, és mindegyik a lasagne elkészítésével töltött időhöz kapcsolódik.

## 1. Határozd meg a várható sütési időt percekben

Valósítsd meg a `Lasagna` osztály `expectedCookTime` függvényét, amely nem fogad argumentumot, és visszaadja, hány percig kell a lasagnének a sütőben lennie.
A szakácskönyv szerint a várható sütési idő 40 perc:

```php
<?php
$timer = new Lasagna();
$timer->expectedCookTime()
// => 40
```

## 2. Számítsd ki a hátralévő sütési időt percekben

Valósítsd meg a `Lasagna` osztály `remainingCookTime` függvényét, amely argumentumként megkapja, hány perce van már a sütőben a lasagne, és visszaadja, hány percet kell még a sütőben maradnia, az előző részfeladatban megadott várható sütési idő alapján.

```php
<?php
$timer = new Lasagna();
$timer->remainingCookTime(30)
// => 10
```

## 3. Számítsd ki az előkészítési időt percekben

Valósítsd meg a `Lasagna` osztály `totalPreparationTime` függvényét, amely argumentumként megkapja, hány réteget raktál a lasagnébe, és visszaadja, hány percet töltöttél a lasagne előkészítésével, feltéve, hogy egy réteg előkészítése 2 percet vesz igénybe.

```php
<?php
$timer = new Lasagna();
$timer->totalPreparationTime(3)
// => 6
```

## 4. Számítsd ki a teljes munkával töltött időt percekben

Valósítsd meg a `Lasagna` osztály `totalElapsedTime` függvényét, amely két argumentumot kap: az első a lasagnébe rakott rétegek száma, a második pedig az, hogy hány perce van a lasagne a sütőben.
A függvény adja vissza, hogy összesen hány percet dolgoztál a lasagne elkészítésén, ami az előkészítési idő és a lasagne által a sütőben eddig eltöltött idő összege.

```php
<?php
$timer = new Lasagna();
$timer->totalElapsedTime(3, 20)
// => 26
```

## 5. Hozz létre egy értesítést, hogy elkészült a lasagne

Valósítsd meg a `Lasagna` osztály `alarm` függvényét, amely nem fogad argumentumot, és egy üzenetet ad vissza, ami jelzi, hogy a lasagne fogyasztásra kész.

```php
<?php
$timer = new Lasagna();
$timer->alarm()
// => "Ding!"
```

## Source

### Created by

- @neenjaw