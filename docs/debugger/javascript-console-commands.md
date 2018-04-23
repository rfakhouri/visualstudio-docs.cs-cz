---
title: Příkazy konzoly pro JavaScript v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- JavaScript Console commands [UWP apps]
- JavaScript debugging, console [UWP apps]
- debugging JavaScript, console [UWP apps]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
- cordova
ms.openlocfilehash: 2c0151bb0810529f0dad36d72b80a13ae519e8b0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="javascript-console-commands-in-visual-studio"></a>Příkazy konzoly pro JavaScript v sadě Visual Studio
  
 Příkazy slouží k odesílání zpráv a provádět další úlohy v okně konzoly pro JavaScript sady Visual Studio. Příklady, které ukazují, jak používat toto okno najdete v tématu [rychlý úvod: ladění jazyka JavaScript](../debugger/quickstart-debug-javascript-using-the-console.md). Informace v tomto tématu se vztahují na UWP aplikace a aplikace vytvořené pomocí nástroje sady Visual Studio pro Apache Cordova. Informace o podporovaných konzoly příkazy v aplikace Cordova, najdete v části [ladění aplikace](https://taco.visualstudio.com/en-us/docs/debug-using-visual-studio/). Informace o použití konzoly nástroje v Internet Exploreru F12 nástroje najdete v tématu [v tomto tématu](http://msdn.microsoft.com/library/ie/dn255006.aspx).  
  
 Pokud zavření okna konzoly jazyka JavaScript, můžete ji otevřít při ladění v sadě Visual Studio výběrem **ladění** > **Windows** > **JavaScript Konzole**.  
  
> [!NOTE]
>  Pokud okno není k dispozici během relace ladění, ujistěte se, že typ ladicí program je nastaven na **skriptu** ve vlastnostech ladění pro projekt.  
  
## <a name="console-object-commands"></a>příkazy objekt konzoly  
 Tato tabulka ukazuje syntaxe `console` objekt příkazy můžete použít v okně konzoly jazyka JavaScript, nebo že můžete použít k odesílání zpráv do konzoly z vašeho kódu. Tento objekt obsahuje různé formuláře, aby bylo možné rozlišit mezi informační zprávy a chybových zpráv, pokud chcete.  
  
 Můžete použít delší formuláře příkaz `window.console.[command]` Pokud potřebujete, aby nedocházelo k záměně možné s místní objekty s názvem konzoly.  
  
> [!TIP]
>  Starší verze sady Visual Studio nepodporují kompletní sadu příkazů. Pomocí IntelliSense objektu konzoly získat rychlý informace o podporované příkazy.  
  
|Příkaz|Popis|Příklad|  
|-------------|-----------------|-------------|  
|`assert(expression, message)`|Odešle zprávu, pokud `expression` vyhodnotí jako **false**.|`console.assert((x == 1), "assert message: x != 1");`|  
|`clear()`|Vymaže zprávy z okna konzoly, včetně skriptu chybové zprávy a vymaže skript, který se zobrazí v okně konzoly. Skript, který jste zadali do řádku konzoly vstupní nevymaže.|`console.clear();`|  
|`count(title)`|Počet pokusů, které bylo voláno příkaz počet odešle do okna konzoly. Každé volání počet je jedinečně identifikovaný nepovinný `title`.<br /><br /> Existující položku v okně konzoly je identifikována `title` parametr (pokud existuje) a aktualizovat pomocí příkazu count. Není-li vytvořit nový záznam.|`console.count();`<br /><br /> `console.count("inner loop");`|  
|`debug(message)`|Odešle `message` do okna konzoly.<br /><br /> Tento příkaz je stejný jako console.log.<br /><br /> Objekty, které se předávají pomocí příkazu jsou převedeny na hodnotu řetězce.|`console.debug("logging message");`|  
|`dir(object)`|Odešle zadaný objekt do okna konzoly a zobrazí v vizualizér k objektu. Chcete-li prověřit vlastnosti v okně konzoly můžete použití vizualizéru.|`console.dir(obj);`|  
|`dirxml(object)`|Odešle zadaný uzel XML `object` do okna konzoly a zobrazí jako ve stromu uzel XML.|`console.dirxaml(xmlNode);`|  
|`error(message)`|Odešle `message` do okna konzoly. Text zprávy je red a uvedena chyby symbol.<br /><br /> Objekty, které se předávají pomocí příkazu jsou převedeny na hodnotu řetězce.|`console.error("error message");`|  
|`group(title)`|Spustí seskupení pro zprávy odeslané do okna konzoly a odešle nepovinný `title` jako popisek skupiny. Skupiny mohou být použity a zobrazí v zobrazení stromu v okně konzoly.<br /><br /> Příkazy skupiny * můžete usnadnit zobrazit výstup okna konzoly v některých případech, například když se používá model komponent.|`console.group("Level 2 Header");` <br /> `console.log("Level 2");` <br /> `console.group();` <br /> `console.log("Level 3");` <br /> `console.warn("More of level 3");` <br /> `console.groupEnd();` <br /> `console.log("Back to level 2");` <br /> `console.groupEnd();` <br /> `console.debug("Back to the outer level");`|  
|`groupCollapsed(title)`|Spustí seskupení pro zprávy odeslané do okna konzoly a odešle nepovinný `title` jako popisek skupiny. Skupiny, které jsou odesílány prostřednictvím `groupCollapsed` se ve výchozím nastavení v sbaleným zobrazením. Skupiny mohou být použity a zobrazí v zobrazení stromu v okně konzoly.|Využití je stejný jako `group` příkaz.<br /><br /> Podívejte se příklad `group` příkaz.|  
|`groupEnd()`|Ukončí aktuální skupiny.<br /><br /> Požadavky:<br /><br /> Visual Studio 2013|Podívejte se příklad `group` příkaz.|  
|`info(message)`|Odešle `message` do okna konzoly. Symbol informace je uvedena zpráva.|`console.info("info message");`<br /><br /> Další příklady najdete v tématu [formátování výstupu console.log](#ConsoleLog) dál v tomto tématu.|  
|`log(message)`|Odešle `message` do okna konzoly.<br /><br /> Pokud předáte objekt, tento příkaz odešle tento objekt v okně konzoly a zobrazí v vizualizér k objektu. Chcete-li prověřit vlastnosti v okně konzoly můžete použití vizualizéru.|`console.log("logging message");`|  
|`msIsIndependentlyComposed(element)`|Používá se ve službě web apps. Není podporováno v aplikacích pro UPW pomocí jazyka JavaScript.|Není podporováno.|  
|`profile(reportName)`|Používá se ve službě web apps. Není podporováno v aplikacích pro UPW pomocí jazyka JavaScript.|Není podporováno.|  
|`profileEnd()`|Používá se ve službě web apps. Není podporováno v aplikacích pro UPW pomocí jazyka JavaScript.|Není podporováno.|  
|`select(element)`|Vybere zadaný HTML `element` v [Průzkumníka modelu DOM](../debugger/quickstart-debug-html-and-css.md).|Console.Select(element);|  
|`time (name)`|Spustí časovač, která je identifikovaná nepovinný `name` parametr. Při použití s `console.timeEnd`, vypočítá čas, který uplyne mezi `time` a `timeEnd`a odešle výsledek (měřeno v ms) pomocí konzoly `name` řetězec jako předponu. Slouží k povolení instrumentace kód aplikace pro měření výkonu.|`console.time("app start");  app.start();  console.timeEnd("app start");`|  
|`timeEnd(name)`|Zastaví časovač, která je identifikovaná nepovinný `name` parametr. Najdete v článku `time` konzole příkaz.|`console.time("app start"); app.start(); console.timeEnd("app start");`|  
|`trace()`|Odešle trasování zásobníku v okně konzoly. Trasování obsahuje zásobníku volání dokončení a obsahuje informace, třeba název souboru, číslo řádku a počet sloupců.|`console.trace();`|  
|`warn(message)`|Odešle `message` do okna konzoly uvedený odůvodněním symbol upozornění.<br /><br /> Objekty, které se předávají pomocí příkazu jsou převedeny na hodnotu řetězce.|`console.warn("warning message");`|  
  
## <a name="miscellaneous-commands"></a>Další příkazy  
 Tyto příkazy jsou k dispozici také v okně konzoly pro JavaScript (nejsou k dispozici z kódu).  
  
|Příkaz|Popis|Příklad|  
|-------------|-----------------|-------------|  
|`$0`, `$1`, `$2`, `$3`, `$4`|Vrátí zadaný element v okně konzoly. `$0` Vrátí element v Průzkumníku modelu DOM. aktuálně vybranou `$1` vrátí prvek dříve vybraném v Průzkumníku modelu DOM. a tak dále, až čtvrté dříve vybraný prvek.|$3|  
|`$(id)`|Vrátí element podle ID. Jedná se o zástupce příkaz pro `document.getElementById(id)`, kde `id` je řetězec, který představuje ID elementu.|`$("contenthost")`|  
|`$$(selector)`|Vrátí pole elementů, které odpovídají zadané selektor pomocí syntaxe selektor šablon stylů CSS. Jedná se o zástupce příkaz pro `document.querySelectorAll()`.|`$$(".itemlist")`|  
|`cd()`<br /><br /> `cd(window)`|Umožňuje změnit kontext pro vyhodnocení výrazu z okna nejvyšší úrovně výchozí stránky do okna zadaného rámce. Volání metody `cd()` bez parametrů vrátí kontext do okna nejvyšší úrovně.|`cd();`<br /><br /> `cd(myframe);`|  
|`select(element)`|Vybere zadaný element v [Průzkumníka modelu DOM](../debugger/quickstart-debug-html-and-css.md).|`select(document.getElementById("element"));`<br /><br /> `select($("element"));`<br /><br /> `select($1);`|  
|`dir(object)`|Vrátí vizualizér pro zadaný objekt. Chcete-li prověřit vlastnosti v okně konzoly můžete použití vizualizéru.|`dir(obj);`|  
  
## <a name="checking-whether-a-console-command-exists"></a>Kontroluje se, zda existuje příkaz konzoly  
 Můžete zkontrolovat, zda existuje konkrétní příkaz dřív, než se ji použít. Tento příklad zkontroluje existenci `console.log` příkaz. Pokud `console.log` existuje, kód zavolá ho.  
  
```javascript  
if (console && console.log) {  
    console.log("msg");  
}  
  
```  
  
## <a name="examining-objects-in-the-javascript-console-window"></a>Prozkoumání objektů v okně konzoly jazyka JavaScript  
 Můžete používat libovolný objekt, který je v oboru, při použití okna konzoly jazyka JavaScript. Chcete-li prověřit objekt na více systémů oboru v okně konzoly, použijte `console.log` , `console.dir`, nebo jinými příkazy z vašeho kódu. Alternativně můžete pracovat s objektem z okna konzoly i když je v oboru nastavením zarážky v kódu (**zarážek** > **vložit zarážku**).  
  
##  <a name="ConsoleLog"></a> Formátování console.log výstup  
 Pokud předáte více argumentů pro `console.log`, konzole bude považovat za pole argumentů a řetězení výstup.  
  
```javascript  
var user = new Object();  
user.first = "Fred";  
user.last = "Smith";  
  
console.log(user.first, user.last);  
// Output:  
// Fred Smith  
  
```  
  
 `console.log` také podporuje vzory pro nahrazování "printf" k formátování výstupu. Pokud používáte vzory pro nahrazování v prvním argumentu, další argumenty se použije pro nahrazení zadaný vzorců v pořadí, ve kterém se používají.  
  
 Podporovány jsou následující vzory pro nahrazování:  
  
-   %s – řetězec  
     %i - celé číslo  
     %d - celé číslo  
     %f - float  
     %o – objekt  
     %b - binární  
     %x - hexadecimální  
     %e - exponentu  
  
 Zde jsou některé příklady použití vzory pro nahrazování v `console.log`:  
  
```javascript  
var user = new Object();  
user.first = "Fred";  
user.last = "Smith";  
user.age = 10.01;  
console.log("Hi, %s %s!", user.first, user.last);  
console.log("%s is %i years old!", user.first, user.age);  
console.log("%s is %f years old!", user.first, user.age);  
  
// Output:  
// Hi, Fred Smith!  
// Fred is 10 years old!  
// Fred is 10.01 years old!  
```  
  
## <a name="see-also"></a>Viz také  
 [Rychlý úvod: Ladění JavaScriptu](../debugger/quickstart-debug-javascript-using-the-console.md)   
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)