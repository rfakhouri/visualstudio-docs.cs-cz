---
title: Vlastnosti konektorů
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: e76766eb3b90dd2a515c7622217febfaffe313c0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53865255"
---
# <a name="properties-of-connectors"></a>Vlastnosti konektorů
Konektory představují vztahy domén ve vygenerovaném návrháři.

 Další informace najdete v tématu [jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Konektory mají vlastnosti, které jsou uvedeny v následující tabulce.

|Vlastnost|Popis|Výchozí|
|-|-|-|
|Barva|Barva této spojnice.|Black|
|Styl přerušování|Styl přerušování čáry této spojnice (plný, Dash, tečka, DashDot, DashDotDot nebo vlastní).|Plná|
|Styl počátku|Styl počátku této spojnice (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond nebo žádný).|Žádná|
|Styl konce|Styl konce této spojnice (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond nebo žádný).|Žádná|
|Barva textu|Barva, která je použitá pro dekoratéry textu, které jsou spojeny s tímto konektorem.|Black|
|Tloušťka|Tloušťka čáry této spojnice v palcích.|0.03125|
|Modifikátor přístupu|Úroveň přístupu třídy (`public` nebo `internal`).|Public|
|Vlastní atributy|Použít k přidání atributů do třídy zdrojový kód, který je generován z tohoto konektoru.|\<žádné >|
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z konektoru nástroje (`none`, `abstract` nebo `sealed`).|žádná|
|Základní spojnice|Základní třída tento konektor.|(žádné)|
|Název|Název tohoto konektoru.|Aktuální název|
|Obor názvů|Obor názvů, který je přidružen s tímto konektorem.|Aktuální obor názvů|
|Popis typu|Jak popisek je definován (fixní, proměnná nebo žádný). Pokud pevně daná, a potom hodnoty `Fixed Tooltip Text` vlastnost se používá jako popis tlačítka; Pokud je proměnná, pak popisek je definován ve vlastním kódu.|\<žádné >|
|Poznámky|Neformální poznámky, které jsou spojeny s tímto konektorem.|\<žádné >|
|Styl směrování|Styl, který se používá pro směrování na spojnici. A `Rectilinear` konektor umožňuje pravoúhlé zapíná podle potřeby; `Straight` spojnice nikoli.|Pravoúhlá|
|Vystavené barvu jako vlastnost<br /><br /> Styl přerušování vystavené jako vlastnost<br /><br /> Tloušťka vystavené jako vlastnost<br /><br /> Zpřístupní barvu textu|Pokud `True`, může uživatel nastavit vlastnost stanovených tvaru. Nastavit, klikněte pravým tlačítkem na definici obrazce a klikněte na tlačítko **přidat vystavený**.|False|
|Popis|Používá se k dokumentu vygenerovaného návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u tohoto konektoru.|\<žádné >|
|Pevný Text popisu tlačítka|Text, který se používá pro pevný popis.|\<žádné >|
|Klíčové slovo nápovědy|Klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tento element.|\<žádné >|

## <a name="see-also"></a>Viz také

- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)