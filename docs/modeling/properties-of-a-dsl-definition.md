---
title: Vlastnosti definice DSL
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: a3a1fa8f1c3b6cce8e9f7d19b8f3a07b9ea42cdf
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-a-dsl-definition"></a>Vlastnosti definice DSL
Definování vlastnosti DslDefinition *jazyka domény* vlastnosti definice například číslování verze. DslDefinition vlastnosti se zobrazí v **vlastnosti** okně po kliknutí na tlačítko Otevřít oblast v diagramu *Návrhář jazyk specifické pro doménu*.

 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

 DslDefinition má vlastnosti v následující tabulce:

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|Modifikátor přístupu|Určuje, zda – modifikátor přístupu pro třídu domény veřejné nebo interní.|public|
|Vlastní atributy|Uživatelem definované atributy pro třídu domény.<br /><br /> **Poznámka:** přidat atribut, klikněte na tlačítko Procházet.|\<žádné >|
|Název společnosti|Název aktuální název společnosti v registru systému.|Aktuální název společnosti|
|Název|Název třídy této domény.|Aktuální název|
|Obor názvů|Obor názvů se spojit s touto třídou domény.|Aktuální obor názvů|
|Identifikátor Guid balíčku|Identifikátor guid [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generovaná pro tato DSL balíčku.|\<žádné >|
|Namespace balíčku|Obor názvů pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generovaná pro tato DSL balíčku.|\<žádné >|
|Název produktu|Název produktu, které se zaregistruje pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] generovaná pro tato DSL balíčku.|\<žádné >|
|Poznámky|Poznámky k přidružený ke třídě této domény.|\<žádné >|
|Popis|Popis pro tuto třídu domény.|\<žádné >|
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro tuto třídu domény.|\<žádné >|
|Nápověda – klíčové slovo|Klíčové slovo nápovědy související s touto třídou domény.|\<žádné >|
|Sestavení|Číslo přírůstkové sestavení pro tuto definici jazyka domény.|0|
|Hlavní verze|Číslo přírůstkové hlavní sestavení pro tuto definici jazyka domény.|1|
|Podverze|Číslo přírůstkové menší sestavení pro tuto definici jazyka domény.|0|
|Revize|Číslo pro tuto definici jazyka domény sestavení přírůstkové revize.|0|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)