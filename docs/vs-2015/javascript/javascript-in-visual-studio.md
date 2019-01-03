---
title: JavaScript
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3eee13e-30e4-4bc1-81f5-058d7e379b75
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7944572cda7f5d549355a25f05bcbcf897fe8530
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990987"
---
# <a name="javascript-in-visual-studio"></a>JavaScript ve Visual Studiu 2012
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

JavaScript je prvotřídní jazyk v sadě Visual Studio. Při psaní kódu v jazyce JavaScript v sadě Visual Studio IDE můžete použít téměř všechny standardní editační pomůcky (fragmenty kódu, funkci IntelliSense atd.). Můžete napsat kód jazyka JavaScript pro mnoho typů aplikací a služeb.

 Referenční dokumentaci jazyka JavaScript naleznete v tématu [JavaScript](http://msdn.microsoft.com/library/d1et7k7c\(v=vs.94\).aspx).

 Konkrétní verze sady Visual Studio, nebo konkrétní rozšíření sady Visual Studio, může být nutné vyvíjet typy konkrétní aplikace a služby pomocí HTML a JavaScriptu. Následující seznam obsahuje odkazy na další informace.

- Vytvoření aplikace pro různé platformy pomocí Apache Cordova, [získat Visual Studio Tools pro Apache Cordova](http://go.microsoft.com/fwlink/p/?LinkId=397606).

- Chcete-li vytvořit [Windows Store](http://dev.windows.com/develop), [Windows Phone](http://dev.windows.com/develop)a univerzálních aplikací pro (, které podporují obě platformy), [získat potřebné nástroje](http://dev.windows.com/en-us/develop/downloads).

- Vytvoření cloudové služby, najdete v tématu [webu Microsoft Azure](http://azure.microsoft.com/documentation/).

- Chcete-li vytvořit weby a webové aplikace, [najdete v článku webu ASP.NET](http://www.asp.net/get-started/websites).

  > [!NOTE]
  >  Můžete vytvořit prázdný web ASP.Net a použít pro programování HTML, CSS a JavaScriptu. Soubor Webconfig poskytovaných technologií ASP.NET povolí ladění v sadě Visual Studio (nebo můžete použít nástroje F12 při spuštění aplikace).

  Editor jazyka JavaScript v aplikaci Visual Studio poskytuje podporu technologie IntelliSense. Další informace najdete v tématu [technologie IntelliSense jazyka JavaScript](../ide/javascript-intellisense.md).

## <a name="whats-new-in-javascript"></a>Co je nového v jazyce JavaScript
 Nové funkce pro JavaScript jsou uvedeny v následující tabulce.

|Funkce|Popis|
|-------------|-----------------|
|Třídy|Podporuje novou syntaxi deklarace [třídy](/visualstudio/scripting-docs/javascript/reference/class-statement-javascript).|
|Co|[Co](/visualstudio/scripting-docs/javascript/reference/promise-object-javascript) umožňují snadněji a čisticí asynchronní programování. Promise konstruktory jsou podporovány, spolu s `all` a `race` pomocné metody.|
|Iterátory|Nyní můžete iterovat iterable objekty (včetně polí, jako pole objektů a iterátory), vyvolání hook vlastní iterace pomocí příkazů ke spuštění pro hodnotu každé různé vlastnosti. Další informace najdete v tématu [iterátory a generátory](/visualstudio/scripting-docs/javascript/advanced/iterators-and-generators-javascript). **Poznámka:**  Generátory se zatím nepodporují.|
|Funkce šipky|Funkce šipky (= >) poskytuje syntaxi ve zkráceném tvaru pro `function` – klíčové slovo, které funkce lexikální `this` vazby.|
|Nové metody pro předdefinované objekty|[Objekt Array](/visualstudio/scripting-docs/javascript/reference/array-object-javascript), [Math – objekt](/visualstudio/scripting-docs/javascript/reference/math-object-javascript), [číslo objektu](/visualstudio/scripting-docs/javascript/reference/number-object-javascript), [objekt objektu](/visualstudio/scripting-docs/javascript/reference/object-object-javascript), a [řetězec objektu](/visualstudio/scripting-docs/javascript/reference/string-object-javascript) předdefinované objekty zahrnují mnoho nových funkcí nástroje a vlastnosti pro manipulaci a prohledávaní údaje.|
|Vylepšení literálu objektu|Objektů teď podporují vypočítané vlastnosti, definice stručné metod a syntaxi ve zkráceném tvaru pro vlastnosti, jehož hodnota je inicializována na proměnnou se stejným názvem. Další informace najdete v tématu [vytváření objektů](/visualstudio/scripting-docs/javascript/creating-objects-javascript).|
|Proxy servery|[Proxy servery](/visualstudio/scripting-docs/javascript/reference/proxy-object-javascript) povolit vlastní chování pro objekty.|
|Parametry REST|Zbývající parametry umožňují zapnout po sobě jdoucí argumenty ve volání funkce na pole. Další informace najdete v tématu [funkce](/visualstudio/scripting-docs/javascript/functions-javascript).|
|Spread – operátor|[Operátor rozšíření](/visualstudio/scripting-docs/javascript/reference/spread-operator-decrement-dot-dot-dot-javascript) (`…`) rozšiřuje iterable výrazů do jednotlivé argumenty. Například `a.b(…array)` je přibližně stejná jako `a.b.apply(a, array)`.|
|Symboly|[Symbol](/visualstudio/scripting-docs/javascript/reference/symbol-object-javascript) objekty povolit vlastnosti, které chcete přidat do stávající objekty se žádná možnost rušení s existujícími vlastnostmi objektu, žádné nežádoucí viditelnost a bez dalších dodatcích nekoordinovaná jiným kódem.|
|Řetězce šablon|[Řetězce šablon](/visualstudio/scripting-docs/javascript/advanced/template-strings-javascript) jsou řetězcové literály, které umožňují výrazů má být vyhodnocen a zřetězená s řetězcový literál.|
|Vylepšení kódování Unicode|Vylepšili jsme podporu kódování Unicode. Nový formát sekvence escape například podporuje astral kódových bodů (body kódu obsahující více než čtyři šestnáctkové číslice). Další informace najdete v tématu [speciální znaky](/visualstudio/scripting-docs/javascript/advanced/special-characters-javascript).|
|WeakSet|A [WeakSet](/visualstudio/scripting-docs/javascript/reference/weakset-object-javascript) je kolekce objektů, které mají být uvolněn z paměti Pokud nejsou odkazovat jinde.|
