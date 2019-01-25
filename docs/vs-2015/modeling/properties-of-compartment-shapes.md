---
title: Vlastnosti obrazců oddílů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.compartmentshape
helpviewer_keywords:
- Domain-Specific Language, compartment shape
ms.assetid: 9a9e112d-210d-413b-a44f-0e976a4a78bc
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 69fac0b8ef5c17a8d66d32730e189f2813aa1158
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760663"
---
# <a name="properties-of-compartment-shapes"></a>Vlastnosti obrazců prostoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Obrazce oddílu jsou jedním z obrazce, které můžete použít k zobrazení doménové třídy v jazyka specifického pro doménu. Můžete rozbalit nebo sbalit oddíly.  
  
 Další informace najdete v tématu [jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Obrazce oddílu mají vlastnosti, které jsou uvedeny v následující tabulce.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Rozbalte výchozí stav sbalení|Pokud `Expanded`, sbaleno se zobrazí při vytvoření. Pokud `Collapsed`, nejsou.|Rozbalení|  
|Barva výplně|Barva výplně tohoto obrazce.|White|  
|Režim přechodu výplně|Režim přechodu výplně tohoto obrazce.|Vodorovná|  
|Geometrie|Geometrie tohoto obrazce (obdélník nebo zaoblení obdélníku).|Obdélník|  
|Má výchozí body připojení|Pokud `True`obrazce použije nahoře, dole, vlevo a správný připojovací body ve vygenerovaném návrháři.|False|  
|Jeden oddíl hlavičky je viditelný|Pokud `False`a je obrazec vybrán jeden oddíl, není záhlaví tohoto oddílu viditelné.|Pravda|  
|Barva obrysu|Barva obrysu tohoto obrazce.|Black|  
|Styl přerušování obrysu|Styl přerušování obrysu tohoto obrazce (plný, pomlčku, tečka, DashDot, DashDotDot, vlastní).|Plná|  
|Tloušťka obrysu|Tloušťka obrysu tohoto obrazce.|0.03125|  
|Barva textu|Barva použitá pro dekoratéry textu, které jsou spojeny s tímto obrazcem.|Black|  
|Modifikátor přístupu|Úroveň přístupu obrazec oddílu (`public` nebo `internal`).|Public|  
|Vlastní atributy|Slouží k přidání atributů do třídy zdrojový kód, který je generován z obrazce oddílu|\<žádné >|  
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z obrazec oddílu (`none`, `abstract` nebo `sealed`).|Žádná|  
|Základní obrazec oddílu|Základní třída tohoto obrazce.|(žádné)|  
|Název|Název tohoto obrazce.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružen s tímto obrazcem.|Aktuální obor názvů|  
|Popis typu|Jak popisek je definován (fixní, proměnná nebo žádný). Pokud pevně daná, a potom hodnoty `Fixed Tooltip Text` vlastnost se používá jako popis tlačítka; Pokud je proměnná, pak popisek je definován ve vlastním kódu.|žádná|  
|Poznámky|Neformální poznámky, které jsou spojeny s tímto obrazcem.|\<žádné >|  
|Počáteční výška|Počáteční výška tohoto obrazce v palcích. Obrazce oddílu jde výška oddílu záhlaví a nebude možné změnit.|1|  
|Počáteční šířka|Počáteční šířka tohoto obrazce v palcích.|1,5|  
|Barva výplně vystavené jako vlastnost<br /><br /> Režim přechodu výplně vystavené<br /><br /> Barva obrysu vystavena jako vlastnost<br /><br /> Styl přerušování obrysu vystavena jako vlastnost<br /><br /> Vystavené jako vlastnost zpřístupní tloušťku obrysu<br /><br /> Zpřístupní barvu textu|Pokud `True`, může uživatel nastavit vlastnost stanovených tvaru. Nastavit, klikněte pravým tlačítkem na definici obrazce a klikněte na tlačítko **přidat vystavený**.|False|  
|Popis|Používá se k dokumentu vygenerovaného návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u tohoto obrazce.|\<žádné >|  
|Pevný Text popisu tlačítka|Text, který se používá pro pevný popis.|\<žádné >|  
|Klíčové slovo nápovědy|Klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tento obrazec.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
