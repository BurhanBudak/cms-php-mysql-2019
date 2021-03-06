# Variabler, operationer och `if/else`

* [**Gå till övningar**](#övningar)

## Variabler 

En variabel måste följa en viss namngivning: 

* En variabel startar med **$** följt av namnet på variabeln.
* En variabel måste **starta med en bokstav eller tecknet `_`**
* En variabel får **inte starta med en siffra**
* En variabel får **bara innehålla alfanumeriska karaktärer**(A-z, 0-9, och _ )
* Variabelnamn är **case-sensitive så stor och liten bokstav spelar roll!**

Dessutom så borde en variabel [**enligt standarden**](http://www.php-fig.org/psr/psr-2/) separereras med understreck om namnet innehåller **fler än 1 ord**, även kallat **snake_case**:

```php
$short
$so_short;
$longest_name_ever
$we_super_long_now_gang;                //snake_case    🐍
$weCouldDoLikeThisAsWell;               //camelCase     🐫
$WhateverFloatsYourBoat;                //PascalCase    ???
$boat-floats = false;                   //kebab-case, not recommended
```


### Skriva ut data

* `echo`    
    * Skriver ut information på din sida
* `print`
    * Skriver ut information på din sida
* `var_dump($var_name)`
    * "Dumpar" information på din sida, används för debugging.

_exempel_
```php
<?php
    $huge = 100000000;
    echo $huge;         //I am basically the same as print
    print $huge;        //I am basically the same as echo
    var_dump($huge);    //I print extra metadata about the variable
?>
```

## `if/else`

* [**Forks**](https://daylerees.com/php-pandas-forks/)

Det är skillnad på **tilldelning** och **jämförelse**. I `if`-satser jämför vi saker, därför måste vi använda dubbla likamedtecken: `==`

```php
$age = 30; //assignment, tilldelning, lagra variabel
$age == 30 //comparison, jämförelse, jämföra variabel, detta returnerar true

if($age == 30){
    //It fits! Age is exactly 30
}
```

```php
if(false){
    echo "Skip me please.";
} else if(false){
    echo "Skip me too!";
} else {
    echo "If everything else was false, I must be true!";
}
```
**Kom ihåg att du kan ha `if`-satser inuti andra `if`-satser**

### AND `&&` / OR `||`

Du kan jämföra flera värden inuti en if-sats om du vill. Då måste vi använda `&&` och `||`. Vi kommer återkomma till dessa och använda dem mycket under kursens gång.
```php
if(true && true){
    echo "I will run only if both are true";
}

if(true || false){
    echo "I will run if one is true";
}

if(true && true && true){
    echo "Wow, all these must be true!";
}

```

## Övningar

1.
Skapa en variabel vid namn `$has_header` som innehåller värdet `true` eller `false`. Om värdet är `true` så ska en `<h1>`-tagg skrivas ut, annars ska inte en `<h1>`-tagg skrivas ut.

2.
Går så att föregående kod istället gör ett val så att den antingen skriver ut `<h1>`-tagg eller en `<p>`-tagg. Om värdet är `true` så ska en h1 skrivas ut, om värdet är `false` så ska en `<p>`-tagg skrivas ut.

3.
Skapa en variabel `$age`. Om värdet är under 18 så ska dina sida skriva ut _"Den där energidrycken är bara för vuxna unge man!_. Annars ska din sida skriva ut _"500kr tack"_

4.
_Ms. Syntax Error_ vill ha ett alarm som anger om vattnet kokar eller inte. Hon vill även att man visar när det når 50 grader så att hon är beredd! Om det inte är 50 eller 100 grader så skall det endast säga att det inte kokar.

* Ange hur många grader vattnet är i en variabel.
* Om vattnet är 100 grader skriv ut: "_Vattnet kokar!_"
* Om vattnet är 50 grader skriv ut: _"Det är halvägs nu!"_
* Annars skriv ut: _"Vattnet kokar inte!"_


5.
_Boolean_ gillar att bada, dock tar vattnet ibland slut hemma och dessutom kan värmen variera ganska mycket. Skriv i PHP ett program som kollar om det finns vatten och om det är tillräckligt varmt. _Tips_ du kan ha en `if`-sats inuti en annan `if`-sats.

* Läs in om det finns vatten (`true` / `false`)
* Läs in hur många grader vattnet är.
* Om det finns vatten och det är varmare än 30 grader skriv ut: _”Varsågod och bada!”_
* Om det **INTE** finns vatten eller det är kallare än 30 grader skriv ut: _”Det går inte att bada.”__


6. 
Vi bestämmer oss för att ta sovmorgon och `echoar` ut att vi tar sovmorgon om det är en helgdag `$weekend` eller om vi har semester `$vacation`.

7.
Skriv ut _"Gå upp, gå till jobbet, jobba, jobba, äta lunch"_ om variabeln `$age` är mellan 18 och 65. Om den är under 18 så skriv ut _"EFTERFEST!"_. Om den är över 65 skriv ut _"mmm, finska pinnar."_.

8.
_Iffy_ äger ett stall med hästar av typerna **A-ponny**, **B-ponny** och C-ponny**. _Iffy_ ska för första gången anordna en tävling. Tävlingsreglerna är följande: För att få tävla måste man fyllt **12 år**. För att få tävla på **A-ponny måste man väga under 30kg**, **B-ponny under 50kg** och **C-Ponny under 65kg**.

* Läs in användarens ålder med en variabel.
* Om åldern är under 12 år så:
    * Skriv ut: ”Du är för ung för att tävla!”
* Om åldern inte är under 12 år så
    * Läs in användarens vikt från variabel
    * Om vikten är under eller lika med 30kg skriv ut: ”A-ponny”
    * Om vikten är under eller lika med 50kg, och över 30kg skriv ut ”B-ponny”
    * Om vikten är under eller lika med 65kg och över 50kg skriv ut ”C-ponny”
    * Om vikten är över 65kg skriv ut ”Det finns inga ponnys för denna viktklass”

<summary></summary>

## Lösningsförslag

**Observera att detta är enbart lösningsförslag., det finns många sätt att lösa dessa på**

1.
```php
$has_header = true;
if($has_header){
    echo "<h1> It'sa heading! </h1>";
}
```

<summary></summary>

2.
```php
$has_header = true;
if($has_header){
    echo "<h1> It'sa heading! </h1>";
} else {
    echo "<p> It'sa paragraph! </p>";
}
```

3.
```php
$age = 17;
//$age is less than 18 so this evaluates to `true`
if($age < 18){
    echo "Den där energidrycken är bara för vuxna unge man!";
} else {
    echo "500kr tack";
}

```

4.
```php
$does_it_boil = 100;

if($doesItBoil == 100){
    echo "Det kokar!";
}else if ($doesItBoil == 50){
    echo "Det är halvvägs nu!";
}else{
    echo "Vattnet kokar inte";
}
```

5.
```php
$water = true;
$degrees = 35;

if($water){
    /*Bara om det finns vatten behöver vi kolla hur många grader vattnet är
    annars kan vi hoppa direkt till else-satsen i slutet*/
    //Kolla om graderna är över 30
    if ($degrees > 30){
        echo "Varsågod och bada!";
    /*Om det inte är över 30 så är det under 30, d.v.s vi behöver 
    inte göra en ytterligare if-sats som kollar det */
    }else{
       echo "Det går inte att bada";
    }
    //Om det inte finns vatten kan vi hoppa till en else-sats istället
}else{
    echo "Det går inte att bada";
}
```

6.
```php
$weekend = true;
$vacation = false;

if($vacation){
    echo "Sleep";
} else if ($weekend){
    echo "Sleep";
} else {
    echo "Gotta work!";
}

```

7.
```php
$age = 78;

if($age > 18 && $age < 65){
    echo "Gå upp, gå till jobbet, jobba, jobba, äta lunch";
} else if ($age < 18) {
    echo "EFTERFEST!";
} else {
    echo "mm, finska pinnar";
}
```

8.
```php
/*Vi behöver bara kolla vilken ponny som behövs om ålder är inne, därför kan
vi lägga till de if-satser som kollar vikt inuti vår första if-sats. Det gör 
så att vi slipper köra kod som inte behövs köras. */
$age = 12;
$weight = 50;

if ($age > 12){
    /*Kollar först om vikten är mindre än 30. Vad vi kollar först är dock beroende av
    vilka värden vi förväntar oss, nu förväntar vi oss att de flesta värden ska vara
    under 65. Vi skulle t.ex. kunna kolla först om vikten är över 65*/
    if($weight <= 30){
        echo 'A-ponny';
    //Sedan kollar vi spannet mellan 30 och 50
    }else if($weight <= 50 && $weight > 30){
        echo 'B-ponny';
    //Till sist kollar vi spannet mellan 50 och 65
    }else if($weight <= 65 && $weight > 50){
        echo 'C-ponny';
    }else{
        echo 'Det finns inga ponnys för denna viktklass';
    }
}else{
    echo 'Du är för ung för att tävla!';
}
```
