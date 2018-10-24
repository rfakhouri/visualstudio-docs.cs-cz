---
title: Vlastnosti dekorátorů
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8e439ae8cb73b8fdaf1bce514370a736cbd0b238
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822342"
---
# <a name="properties-of-decorators"></a>Vlastnosti dekorátorů
Dekorátory jsou ikony, text nebo Rozbalit/sbalit dvojité šipky, které se mohou objevit na obrazců a konektorů v diagramu. Následující tabulky popisují vlastnosti pro tři druhy dekoratér. Některé vlastnosti se zobrazí pouze na obrazec dekoratéry nebo pouze na konektor dekorátory.

 Další informace najdete v tématu [jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).

## <a name="expandcollapse-decorator"></a>Dekoratér rozbalení/sbalení

|Vlastnost|Popis|Výchozí|
|-|-|-|
|displayName|Název, který se zobrazí ve vygenerovaném návrháři dekoratér.|Rozbalte sbalit Dekoratér|
|Název|Název dekoratéru|Dekoratér rozbalení a sbalení|
|Poznámky|Neformální poznámky, které jsou spojeny s tohoto dekoratéru|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|OffsetFromLine|Posun dekoratéru v řádku vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéru od obrazce vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí pozici dekoratéru.|SourceTop|

## <a name="icon-decorator"></a>Dekoratér ikony

|Vlastnost|Popis|Výchozí|
|-|-|-|
|DefaultIcon|Cesta souboru ikony nebo obrázku, který se má zobrazit.|\<žádné >|
|displayName|Název dekoratér, který se zobrazí ve vygenerovaném návrháři.|Dekoratér ikony|
|Název|Název dekoratéru|Dekoratér ikony|
|Poznámky|Neformální poznámky, které jsou spojeny s dekoratér.|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|OffsetFromLine|Posun dekoratéru v řádku vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéru od obrazce vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí pozici dekoratéru.|SourceTop|

## <a name="textdecorator"></a>TextDecorator

|Vlastnost|Popis|Výchozí|
|-|-|-|
|DefaultText|Výchozí text, který se má zobrazit.|Popisek|
|displayName|Název dekoratér, který se zobrazí ve vygenerovaném návrháři.|Popisek|
|Velikost písma|Velikost písma textu zobrazeného v dekoratéru.|8|
|fontStyle|Styl písma textu zobrazeného v dekoratéru.|Pravidelné|
|Název|Název dekoratéru|Popisek|
|Poznámky|Neformální poznámky, které jsou spojeny s dekoratér.|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí pozici dekoratéru, v palcích. (Ve tvarech pouze.)|0|
|OffsetFromLine|Posun dekoratéru v řádku vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéru od obrazce vzhledem k jeho výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí pozici dekoratéru.|TargetBottom|

## <a name="see-also"></a>Viz také

- [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)