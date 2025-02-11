---
title: 'Začínáme s PTVS: Interaktivní Python | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-python
ms.topic: conceptual
ms.assetid: fa594314-bdd0-4da5-874a-57b03414b675
caps.latest.revision: 5
author: kraigb
ms.author: kraigb
manager: jillfra
ms.openlocfilehash: 4fba8bf658a50a7a7e28abace1eb622ab14f5f26
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62550984"
---
# <a name="getting-started-with-ptvs-interactive-python"></a>Začínáme s PTVS: Interaktivní Python
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Interaktivní výzvy nebo čtení eval-print smyčky (REPLs) jsou klíče nástroje pro produktivitu programovacích jazyků.  Umožňují spouštět fragmenty kódu pro zjišťování a další rozhraní API a experimentovat s použitím rozhraní API a interaktivně vyvíjet pracovní kód přikazující zahrnutí v projektech nebo programy.  
  
 Můžete sledovat tyto pokyny ve velmi krátké [videa youtube](https://www.youtube.com/watch?v=yc2CROtTsC0&index=5&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff).  
  
 V okně prostředí Pythonu najdete v seznamu všechna prostředí Pythonu.  Můžete vybrat některou z nich otevřít interaktivní okno nebo REPL.  Pokud jste někdy spustili Python.exe v příkazovém řádku, pak jste viděli python REPL před.  REPL výzvu a zadáte kód, stiskněte klávesu enter a ihned sledujte výsledky vašeho kódu.  Toto je živé spuštění kontext, který zahrnuje všechny stavy všech spuštění, přiřazení proměnných, atd.  Mohou odkazovat na proměnné obsahující výsledky v pozdější příspěvkům poskytnutým prostřednictvím REPL příkazový řádek.  Můžete napsat více řádků kódu a spouštějte je všechny najednou (třeba deklarace metody nebo více příkazů).  
  
 Když začnete používat novou knihovnu, REPL je skvělý způsob, jak vyzkoušet knihovny.  Můžete importovat knihovny, zkontrolovat balíčky sub, třídy a funkce.  Python se dozvíte vše z těchto informací prostřednictvím jeho `help()` funkce.  Navíc nástroje Python Tools pro Visual Studio (PTVS) poskytuje návrhy a podle jeho modelování kód použitý v editoru, což se provádí, aniž by bylo nutné provést knihovny dokumentace.  Když je kód spuštěn, použije PTVS informace z modulu runtime Pythonu ke zlepšení PTVS návrhy.  
  
 Interaktivní okno je také užitečné pro vývoj iterativní nebo evoluční kódu, včetně testování kódu při vývoji.  Můžete vybrat funkci v okně editoru, stiskněte tlačítko vpravo ukazatele a zvolte možnost odeslat do Interactive.  Tento příkaz zkopíruje výběr do interaktivního okna jako další vstup a spustí ho.  Okamžitě uvidíte výsledky.  Pokud potřebujete provést změny na předchozí vstup, můžete ke spouštění kódu vytvořeného stiskněte šipkou nahoru můžete vrátit kód, upravit ji a stiskněte kombinaci kláves Ctrl + Enter.  Stisknutím klávesy Enter na konci vstupu spustí, ale stisknutím klávesy Enter uprostřed vstup vloží nový řádek.  
  
 Můžete otevřít interaktivní okno pro každou instalaci Pythonu, tolik, jak potřebujete.  Existují tlačítka v horní části okna zobrazení vymazat, resetovat kontextu spuštění, atd.  Historie se nijak nezmění.  
  
 Můžete sledovat tyto pokyny ve velmi krátké [videa youtube](https://www.youtube.com/watch?v=yc2CROtTsC0&index=5&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff).  
  
## <a name="see-also"></a>Viz také  
 [Dokumentace ke službě Wiki](https://github.com/Microsoft/PTVS/wiki/Interactive-REPL)   
 [Videa můžete začít a Deep Dive PTVS](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)
