---
title: Určení, kdy a kde se má poznámka použít
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Group_
- _At_
- _When_
- _At_buffer_
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 6c7adb310db9eece1d8d4a2881057cc1acde1062
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923820"
---
# <a name="specifying-when-and-where-an-annotation-applies"></a>Určení, kdy a kde se má poznámka použít
Pokud je Poznámka podmíněná, může vyžadovat další poznámky k určení tohoto analyzátoru.  Například pokud má funkce proměnnou, která může být buď synchronní, nebo asynchronní, funkce se chová takto: V případě synchronního případu to vždy proběhne úspěšně, ale v asynchronním případě hlásí chybu, pokud nemůže být okamžitě úspěšná. Pokud je funkce volána synchronně, kontrola hodnoty výsledku neposkytne analyzátoru kódu žádnou hodnotu, protože by nebyla vrácena.  Nicméně pokud je funkce volána asynchronně a výsledek funkce není kontrolován, může dojít k závažné chybě. Tento příklad znázorňuje situaci, ve které byste mohli použít `_When_` anotaci popsanou dále v tomto článku – Chcete-li povolit kontrolu.

## <a name="structural-annotations"></a>Strukturální poznámky
Chcete-li určit, kdy a kde se poznámky vztahují, použijte následující strukturální poznámky.

|Poznámka|Popis|
|----------------|-----------------|
|`_At_(expr, anno-list)`|`expr`je výraz, který vrací lvalue. Poznámky v `anno-list` jsou aplikovány na objekt, který je `expr`pojmenován. Pro každou anotaci `anno-list`v `expr` je interpretována v předběžné podmínce, pokud je Poznámka interpretována v předběžné podmínce, a v případě, že je Poznámka interpretována v podmínkách post.|
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr`je výraz, který vrací lvalue. Poznámky v `anno-list` jsou aplikovány na objekt, který je `expr`pojmenován. Pro každou anotaci `anno-list`v `expr` je interpretována v předběžném stavu, pokud je Poznámka interpretována v předběžné podmínce, a v případě, že je Poznámka interpretována v podmínkách post.<br /><br /> `iter`je název proměnné, která je vymezena na anotaci (včetně `anno-list`). `iter`má implicitní typ `long`. Identicky pojmenované proměnné v jakémkoli ohraničujícím oboru jsou ze hodnocení skryté.<br /><br /> `elem-count`je výraz, který je vyhodnocen jako celé číslo.|
|`_Group_(anno-list)`|Poznámky v `anno-list` jsou všechny považované za všechny kvalifikátory, které se vztahují k poznámce skupiny, která se používá u každé poznámky.|
|`_When_(expr, anno-list)`|`expr`je výraz, který lze převést na `bool`. Pokud je hodnota nenulová (`true`), poznámky, které jsou určeny v `anno-list` , jsou považovány za použitelné.<br /><br /> Ve výchozím nastavení je pro každou anotaci `expr` v `anno-list`, interpretován jako použití vstupních hodnot, pokud je Poznámka podmínkou, a jako výstupních hodnot, pokud je Poznámka podmínkou. Chcete-li přepsat výchozí hodnotu, můžete použít `_Old_` vnitřní při vyhodnocení podmínky post, aby označovala, že by měly být použity vstupní hodnoty. **Poznámka:**  Různé poznámky mohou být povoleny jako důsledek použití `_When_` , je-li zahrnuta proměnlivá hodnota ( `*pLength`například), `expr` protože vyhodnocený výsledek v předběžné podmínce se může lišit od vyhodnoceného výsledku v podmínkách post.|

## <a name="see-also"></a>Viz také

- [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Porozumění SAL](../code-quality/understanding-sal.md)
- [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)
- [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)
- [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)
- [Vnitřní funkce](../code-quality/intrinsic-functions.md)
- [Doporučené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)