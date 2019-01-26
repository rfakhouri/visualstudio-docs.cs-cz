---
title: Vlastnosti diagramů
ms.date: 10/31/2018
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: cf3405d74a1545bb86b1297b766faf46e68223a4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942045"
---
# <a name="properties-of-diagrams"></a>Vlastnosti diagramů
Můžete nastavit vlastnosti, které určují, jak diagramy se zobrazí ve vygenerovaném návrháři. Můžete například zadat výchozí barva textu v diagramu.

 Další informace najdete v tématu [jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).

 V následující tabulce jsou uvedeny vlastnosti diagramů.

|Vlastnost|Popis|Výchozí|
|-|-|-|
|Barva výplně|Barva výplně diagramu.|White|
|Barva textu|Barva textu, který se zobrazí v diagramu.|Black|
|Modifikátor přístupu|Modifikátor přístupu třídy (veřejné nebo interní).|Public|
|Vlastní atributy|Umožňuje přidat atributy vytvořené třídě kódu.|\<žádné >|
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepsat a rozšiřování vygenerovaných tříd](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepsat a rozšiřování vygenerovaných tříd](../modeling/overriding-and-extending-the-generated-classes.md)...|False|
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z diagramu (`none`, `abstract`, nebo `sealed`).|Žádná|
|Základní Diagram|Základní třída tento diagram.|(žádné)|
|Název|Název tohoto diagramu.|Aktuální název|
|Obor názvů|Obor názvů, který je přidružený tento diagram.|Aktuální obor názvů|
|Reprezentovaná třída|Kořenová třída domény, který představuje tento diagram.|Pokud je k dispozici aktuální kořenová třída|
|Poznámky|Neformální poznámky, které jsou spojeny s tímto elementem.|\<žádné >|
|Barva výplně zveřejní jako vlastnost|Pokud `True`, může uživatel nastavit barvu výplně diagramu vygenerovaného návrháře. Pokud chcete nastavit tuto vlastnost, klikněte pravým tlačítkem na obrazec diagram a klikněte na **přidat vystavený**.|False|
|Zpřístupní barvu textu jako vlastnost|Pokud `True`, může uživatel nastavit barvu textu diagramu ve vygenerovaném návrháři. Pokud chcete nastavit tuto vlastnost, klikněte pravým tlačítkem na obrazec diagram a klikněte na **přidat vystavený**.|False|
|Popis|Popis, který se používá k dokumentu vygenerovaného návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u tohoto diagramu.|\<žádné >|
|Klíčové slovo nápovědy|Klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tento diagram.|\<žádné >|

## <a name="see-also"></a>Viz také:

[Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
