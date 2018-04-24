---
title: Vlastnosti drah
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.swimlane
helpviewer_keywords:
- Domain-Specific Language, swimlane
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: b9ffdf12daa93da9a5f7190866682bc60401dbcc
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-swimlanes"></a>Vlastnosti drah
Plaveckých drah můžete přidat do diagramu. Plaveckých drah rozdělení diagram na svislé nebo vodorovné oblasti. Můžete definovat, která se zobrazí uvnitř plaveckých drah ostatním tvarům. Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Plaveckých drah mít vlastnosti, které jsou uvedeny v následující tabulce.

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|Barva výplně textu|Barva výplně pro text dráha.|prázdné|
|Barva výplně záhlaví|Barva výplně pro hlavičku dráha.|DarkGray|
|Barva oddělovače|Barva čáry oddělovače.|LightGray|
|Styl čáry oddělovače|Styl čáry oddělovače (`Solid`, `Dash`, `Dot`, `DashDot`, `DashDotDot`, nebo `Custom`).|`Dash`|
|Tloušťka oddělovače|Tloušťka čáry oddělovače v palcích.|0.03125|
|Barva textu|Barva, který se používá pro dekoratéry textu, které jsou přidruženy tento dráha.|černé|
|Modifikátor přístupu|Úroveň přístupu třídy (`public` nebo `internal`).|Public|
|Vlastní atributy|Použít k přidání atributů do kódu třídu, která se generují z této dráha.|\<žádné >|
|Generuje dvojitou odvozené|Pokud `True`, budou generovány základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Má vlastní – konstruktor|Pokud `True`, bude k dispozici vlastní konstruktor v zdrojového kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Modifikátor dědičnosti|Popisuje typ dědičnost třídy zdrojového kódu, která se generují z dráha (`none`, `abstract` nebo `sealed`).|žádná|
|Základní dráha|Základní třída této dráha.|(žádný)|
|Název|Název této dráha.|Aktuální název|
|Obor názvů|Obor názvů, který je přidružený tento dráha.|Aktuální obor názvů|
|ToolTip – typ|Jak je definována v popisu tlačítka (`fixed`, `variable`, nebo `none`). Pokud `fixed`, pak hodnota `Fixed Tooltip Text` vlastnost je použita; Pokud `variable`, pak popisek je definována v vlastní kód.|\<žádné >|
|Poznámky|Neformální poznámky, které jsou přidruženy tento dráha.|\<žádné >|
|Zarovnání|Vodorovné nebo svislé zarovnání.|Svislý|
|Počáteční výšku.|Počáteční výška tento dráha v palcích. Platí pouze pro vodorovné plaveckých drah.|0|
|Počáteční šířka|Počáteční šířka tento dráha v palcích. Platí pouze pro svislé plaveckých drah.|0|
|Barva textu zpřístupňuje|Pokud `True`, může uživatel nastavit barvy dráha v Návrháři vygenerovaný. Chcete-li tuto možnost nastavíte, klikněte pravým tlačítkem na obrazec dráha a klikněte na **přidat zveřejněné**.|False|
|Popis|Používá k dokumentu generovaný návrháře.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí v Návrháři generovaného odkazovat na tuto třídu dráha.|\<žádné >|
|Opravené Text popisku|Text, který se používá pro pevnou popisek.|\<žádné >|
|Nápověda – klíčové slovo|Klíčové slovo, které se používá k indexu F1 – Nápověda pro tento dráha.|\<žádné >|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)