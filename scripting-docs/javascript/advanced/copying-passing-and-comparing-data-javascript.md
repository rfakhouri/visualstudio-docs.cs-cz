---
title: "Kopírování, předávání a porovnávání dat (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [Visual Studio], passing values
- function parameters
- string comparison
- function parameters, about function parameters
- ByRef argument
- arrays [Visual Studio], setting data types
- arrays [Visual Studio], copying data
- ByVal argument
- string comparison, testing data
ms.assetid: fbccd877-7249-45d4-bd9f-6bcd8ba94a6b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3cf980ca1dfd0c0e09871b6de9756cb2a10364b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="copying-passing-and-comparing-data-javascript"></a>Kopírování, předávání a porovnávání dat (JavaScript)
V [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)], jak se zpracují data závisí na jeho datového typu.  
  
## <a name="by-value-vs-by-reference"></a>Podle hodnoty vs. Odkazem  
 Čísla a logické hodnoty (**true** a **false**) jsou zkopírovány, předání a porovnání *hodnotou*. Při kopírování nebo předávání hodnotou alokujete v paměti počítače určité místo a zkopírujete do něj hodnotu originálu. Pokud pak originál změníte, není kopie nijak ovlivněna (a naopak), protože se jedná o dvě samostatné entity.  
  
 Objekty pole a funkce jsou zkopírovány předán a porovnání *odkazem*. Při kopírování nebo předávání odkazem v podstatě vytvoříte ukazatel na originální položku a použijete tento ukazatel, jako by to byla kopie. Pokud pak originál změníte, změní se jak originál, tak kopie (a naopak). Reálně existuje pouze jedna entita; „kopie“ ve skutečnosti není kopie, ale pouze další odkaz na data.  
  
 Při porovnávání odkazem musí obě proměnné odkazovat na přesně stejnou entitu, aby bylo porovnání úspěšné. Například dvě odlišné **pole** objektů bude vždy porovnat jako různé, i v případě, že obsahují stejné prvky. Aby bylo porovnání úspěšné, musí být jedna z proměnných odkazem na druhou. Pokud chcete zkontrolovat, pokud se dvěma poli obsahovat stejné prvky, porovnejte výsledky **toString()** metoda.  
  
 Řetězce se kopírují a předávají odkazem, ale porovnávají hodnotou. Všimněte si, že pokud máte dva **řetězec** objekty (vytvořené pomocí **nové** String("something")), jsou porovnávány s odkazem, ale pokud jedna nebo obě hodnoty řetězcovou hodnotu, jsou porovnávány hodnotou.  
  
> [!NOTE]
>  Vzhledem ke způsobu, jakým jsou sestaveny znakové sady ASCII a ANSI, se velká písmena nacházejí v posloupnosti před malými písmeny. Například "Zoo" porovná jako *méně* než "aardvark." Můžete volat **toUpperCase()** nebo **toLowerCase()** na oba řetězce, pokud chcete provést porovnávání.  
  
## <a name="passing-parameters-to-functions"></a>Předávání parametrů funkcím  
 Při předávání parametru určité funkci hodnotou vytvoříte samostatnou kopii tohoto parametru, která existuje pouze uvnitř této funkce. Ačkoli se objekty a pole předávají odkazem, pokud je přímo přepíšete novou hodnotou ve funkci, nepromítne se nová hodnota vně této funkce. Vně funkce jsou viditelné pouze změny vlastností objektů nebo prvků pole.  
  
 Příklad (použití objektového modelu aplikace Internet Explorer):  
  
```JavaScript  
// This clobbers (over-writes) its parameter, so the change  
// is not reflected in the calling code.  
function Clobber(param)   
{  
    // clobber the parameter; this will not be seen in   
    // the calling code  
    param = new Object();  
    param.message = "This will not work";  
}  
  
// This modifies a property of the parameter, which  
// can be seen in the calling code.  
function Update(param)  
{  
    // Modify the property of the object; this will be seen  
    // in the calling code.  
    param.message = "I was changed";  
}  
  
// Create an object, and give it a property.  
var obj = new Object();  
obj.message = "This is the original";  
  
// Call Clobber, and print obj.message. Note that it hasn't changed.  
Clobber(obj);  
window.alert(obj.message); // Still displays "This is the original".  
  
// Call Update, and print obj.message. Note that is has changed.  
Update(obj);  
window.alert(obj.message); // Displays "I was changed".  
```  
  
## <a name="testing-data"></a>Testování dat  
 Při provádění testu pomocí hodnoty se porovnáním dvou rozdílných položek zjišťuje, zda jsou si rovny. Obvykle se toto porovnání provádí bajt po bajtu. Při testování pomocí odkazu se kontroluje, zda dvě položky ukazují na jedinou originální položku. Pokud ano, jsou vyhodnoceny jako shodné; pokud ne, jsou vyhodnoceny jako neshodné, přestože obsahují přesně stejné hodnoty bajt po bajtu.  
  
 Kopírování a předávání řetězců odkazem šetří paměť; protože ale řetězce po vytvoření nelze změnit, je možné je porovnat pomocí hodnoty. Tímto způsobem můžete otestovat, zda mají dva řetězce stejný obsah, i když byl jeden řetězec vygenerován zcela odděleně od druhého.  
  
## <a name="see-also"></a>Viz také  
 [Výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)