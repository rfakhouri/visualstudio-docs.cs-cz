---
title: Vlastnosti diagramů
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: bd02bd7f91d80392553d4c9f5e7ff10ab71b1abe
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-diagrams"></a>Vlastnosti diagramů
Můžete nastavit vlastnosti, které určují, jak diagramy se zobrazí v Návrháři vygenerovaný. Můžete například zadat výchozí barvu textu v diagramu.

 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Následující tabulka uvádí vlastnosti diagramů.

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|Barva výplně|Barva výplně diagramu.|prázdné|
|Barva textu|Barva textu, který se zobrazí v diagramu.|černé|
|Modifikátor přístupu|Modifikátor přístupu – třída (veřejné nebo interní).|Public|
|Vlastní atributy|Použít k přidání atributů do třídy generovaného kódu.|\<žádné >|
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md)...|False|
|Modifikátor dědičnosti|Popisuje typ dědičnost třídy zdrojového kódu, která se generují z diagramu (`none`, `abstract` nebo `sealed`).|Žádné|
|Základní Diagram|Základní třída tohoto diagramu.|(žádný)|
|Název|Název tohoto diagramu.|Aktuální název|
|Obor názvů|Obor názvů, který je přidružený tohoto diagramu.|Aktuální obor názvů|
|Třída je reprezentovaná|Třída kořenové domény, která představuje tohoto diagramu.|Pokud je k dispozici aktuální kořenová třída|
|Poznámky|Neformální poznámky, které jsou spojeny s tímto elementem.|\<žádné >|
|Barva výplně zpřístupňuje jako vlastnost|Pokud `True`, může uživatel nastavit barvu výplně diagram generovaný návrháře. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na tvar diagram a klikněte na **přidat Explosed**.|False|
|Zpřístupní barvy jako vlastnost|Pokud `True`, může uživatel nastavit v Návrháři generované barvy diagramu. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na tvar diagram a klikněte na **přidat Explosed**.|False|
|Popis|Popis, který se používá k dokumentu generovaný návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro toto schéma.|\<žádné >|
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tohoto diagramu.|\<žádné >|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)