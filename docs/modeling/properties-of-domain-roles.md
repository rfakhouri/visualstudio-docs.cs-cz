---
title: Vlastnosti rolí domény | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 00ed4a86f2a00f9317f198d925fddbbc7f115481
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-domain-roles"></a>Vlastnosti rolí domény
Vlastnosti v následující tabulce jsou přidružené k roli domény. Informace o rolích domény najdete v tématu [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|Typ kolekce|Pokud tato role má násobnost 0.. * nebo 1... \*, tato vlastnost přizpůsobí obecný typ, který se používá k ukládání kolekci odkazů.|`(none)` - <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601> se používá|
|Vlastní atributy|Atributy, které zde určíte budou přidáni jako atributy pro třídu generovaného kódu.|< žádné\>|
|Je-li vlastnost procházet|Pokud `True`, a pokud násobnost relací 0..1 nebo 1..1, mohou vlastnost role uživatele v Procházet **vlastnosti** okno. Vlastnost zobrazí název elementu na druhém konci vztahu odkazu.|`True`|
|Je generátor vlastnost|Pokud `True`, vlastnost role se vygeneruje pro tuto roli, který můžete použít k procházení relace v programovém kódu. Pokud nastavíte hodnotu false, mohou procházet relace méně efektivní způsobem pomocí statické metody třídy relace domény.|`True`|
|Modifikátor přístupu metoda Getter vlastnosti|Modifikátor přístupu pro getter pro vlastnost generovaného (`public`, `internal`, `private`, `protected`, nebo `protected internal`).|`public`|
|Modifikátor přístupu metoda Setter vlastnosti|Modifikátor přístupu pro setter pro vlastnost generovaného (`public`, `internal`, `private`, `protected`, nebo `protected internal`).|`public`|
|Násobnost|Počet elementů modelu, které můžete přehrát opačné role (`0..1`, `1..1`, `0..*`, nebo `1..*`). Pokud je násobnost `0..*` nebo `1..*`, pak vlastnost generovaného představuje kolekci; jinak hodnota generovaného vlastnost představuje element jeden model.|Závisí na typu relace a jestli je to zdrojová nebo cílová role v relaci.|
|Název|Název role domény. Tato vlastnost nesmí obsahovat prázdné znaky.|Název třídy domény přehrávače role pro tuto roli.|
|Rozšíří kopie|`DoNotPropagateCopy` -Player zkopírovaný role budou mít žádné kopii tohoto odkazu.<br /><br /> `PropagateCopyToLinkOnly` -Zkopírovaný odkaz ukazuje na existující opačným role player.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer` -Zkopírovaný odkaz odkazuje na kopii opačné player role.|`PropagateCopyToLinkAndOppositeRolePlayer` pro zdrojové role vkládaných.<br /><br /> `DoNotPropagateCopy` pro jiné role.<br /><br /> Další informace najdete v tématu [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md)|
|Rozšíří odstranění|`True` Chcete-li odstranit elementu, který hraje tato role při odstranění odkaz související.|`True` pro cíl vnoření role.<br /><br /> `False` pro jiné role.<br /><br /> Další informace najdete v tématu [přizpůsobení chování při odstranění](../modeling/customizing-deletion-behavior.md).|
|Název vlastnosti|Název vlastnosti vygenerovaných kód role player. Tento název nesmí obsahovat prázdné znaky.|Název opačné role, pokud tato role má nule: 1 nebo 1: 1 násobnost; v opačném pluralized název opačné role.|
|Role Player|Třída domény elementu, který můžete přehrát této role v relaci. Tato vlastnost je pouze pro čtení.|Třída domény přehrávače role pro tuto roli.|
|Poznámky|Neformální poznámky, které jsou přidruženy role domény.|< žádné\>|
|Kategorie|Kategorie, pod kterým generovaného vlastnost se zobrazí v **vlastnosti** okno v Návrháři vygenerovaný. Pokud je tato vlastnost prázdná, pak vlastnost generovaného se objeví pod uzlem **různé** kategorie|< žádné\>|
|Popis|Popis, který se používá k dokumentu kódu a používá se v uživatelském rozhraní vygenerovaný návrháře.<br /><br /> Popis se zobrazí v popisu tlačítka technologie IntelliSense pro vlastnost vygenerovaný na třídě player role.|`Description for` *úplný název role*|
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro role domény.|Upravená hodnota vlastnosti Name.|
|Nápověda – klíčové slovo|Volitelné klíčové slovo, které se používá k indexu F1 – Nápověda pro role domény.|\<žádné >|
|Zobrazovaný název vlastnosti|Název, který se zobrazí v Návrháři generovaný pro vlastnost generovaného role.|Upravená hodnota vlastnosti název vlastnosti.|

> [!NOTE]
>  Výchozí hodnota zobrazovaný název vychází hodnotu přidružené vlastnosti vložením mezer před každý velká znak, který je malá znak a který není následnou jiné velké písmeno.

## <a name="see-also"></a>Viz také
 [Vlastnosti vztahů domény](../modeling/properties-of-domain-relationships.md)