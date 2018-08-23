---
title: Určení, kdy a kde se má poznámka použít | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- _Group_
- _At_
- _When_
- _At_buffer_
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
caps.latest.revision: 9
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9ca11e9339534c1053a62442f4eb2e4a65ca2a62
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678708"
---
# <a name="specifying-when-and-where-an-annotation-applies"></a>Určení, kdy a kde se má poznámka použít
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zadání při a kde Poznámka použít](https://docs.microsoft.com/visualstudio/code-quality/specifying-when-and-where-an-annotation-applies).  
  
Po podmíněné Poznámka se může vyžadovat další poznámky a určit, že analyzátor.  Například pokud je funkce, které mohou být synchronní nebo asynchronní proměnné, funkce se chová takto: V případě synchronní je vždy nakonec úspěšná, ale v případě asynchronní oznámí chybu Pokud nemůže být okamžitě úspěšná. Když je zavolána funkce synchronně, kontrolou hodnoty výsledku poskytuje převáděná hodnota analyzátor kódu, protože nebude mít vrátil.  Když je tato funkce volána asynchronně a výsledek funkce není povolená, může dojít k závažné chybě. Tento příklad ukazuje situaci, ve kterém můžete použít `_When_` anotace – je popsáno dále v tomto článku – Povolení kontroly.  
  
## <a name="structural-annotations"></a>Strukturální poznámky  
 Pokud chcete řídit, kdy a kde použít poznámky, použití následující strukturální anotací.  
  
|Poznámka|Popis|  
|----------------|-----------------|  
|`_At_(expr, anno-list)`|`expr` je výraz, jehož výsledkem jsou l-hodnota. Poznámky v `anno-list` aplikují i na objekt, který je pojmenován podle `expr`. Pro jednotlivé poznámky v `anno-list`, `expr` interpretována v předběžné podmínce, pokud anotace je interpretován v předběžné podmínce, a pokud podmínka po Poznámka je interpretován po stavu.|  
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr` je výraz, jehož výsledkem jsou l-hodnota. Poznámky v `anno-list` aplikují i na objekt, který je pojmenován podle `expr`. Pro jednotlivé poznámky v `anno-list`, `expr` interpretována v předběžné podmínce, pokud anotace je interpretován v předběžné podmínce, a pokud podmínka po Poznámka je interpretován po stavu.<br /><br /> `iter` je název proměnné, která působí na poznámku (inclusive z `anno-list`). `iter` má implicitní typ `long`. Ze zkušební verze jsou skryté identicky pojmenovanou proměnné v ohraničujícím oboru.<br /><br /> `elem-count` je výraz vyhodnocen jako celé číslo.|  
|`_Group_(anno-list)`|Poznámky v `anno-list` jsou všechny považovány za jakékoli kvalifikátor, které platí pro skupiny anotace, které platí pro jednotlivé poznámky.|  
|`_When_(expr, anno-list)`|`expr` je výraz, který lze převést na `bool`. Když je nenulová (`true`), poznámky, které jsou určené v `anno-list` jsou považovány za použít.<br /><br /> Ve výchozím nastavení pro jednotlivé poznámky v `anno-list`, `expr` je interpretován jako pomocí vstupní hodnoty, pokud anotace je předpokladem a Poznámka pomocí výstupní hodnoty, pokud je po podmínku. Chcete-li přepsat výchozí nastavení, můžete použít `_Old_` vnitřní při vyhodnocení po podmínky k označení, že má být použit vstupní hodnoty. **Poznámka:** různých poznámek může povolit následkem pomocí `_When_` Pokud proměnlivé hodnoty – například `*pLength`– je zahrnuta, protože Vyhodnocená výsledek `expr` v předběžné podmínce může lišit od jeho Vyhodnocená Výsledkem po podmínku.|  
  
## <a name="see-also"></a>Viz také  
 [Použití poznámek SAL k omezení defektů kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Porozumění SAL](../code-quality/understanding-sal.md)   
 [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)   
 [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)   
 [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)   
 [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)   
 [Vnitřní funkce](../code-quality/intrinsic-functions.md)   
 [Osvědčené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)



