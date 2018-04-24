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
ms.technology: vs-ide-modeling
ms.openlocfilehash: d99ec880b00583726b0f0c3aa7368b0f5860f847
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-decorators"></a>Vlastnosti dekorátorů
Dekoratéry jsou ikony, text nebo dvojitou šipkou rozbalit nebo sbalit, které se mohou objevit na tvary nebo konektory v diagramu. Vlastnosti pro tři druhy dekoratéra naleznete v následujících tabulkách. Některé vlastnosti se zobrazí pouze na tvar dekoratéry nebo pouze na dekoratéry konektor.

 Další informace najdete v tématu [jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

## <a name="expandcollapse-decorator"></a>Rozbalit nebo sbalit Dekoratéra

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|displayName|Název dekoratéra, který se zobrazí v Návrháři vygenerovaný.|Rozbalte položku sbalit Dekoratéra|
|Název|Název dekoratéra.|ExpandCollapseDecorator|
|Poznámky|Neformální poznámky, které jsou přidruženy tento dekoratéra.|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|OffsetFromLine|Posun dekoratéra z řádku vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéra z tvaru vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí umístění dekoratéra.|SourceTop|

## <a name="icon-decorator"></a>Ikona Dekoratéra

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|DefaultIcon|Cesta souboru ikony nebo obrázku má být zobrazen.|\<žádné >|
|displayName|Název dekoratéra, který se má zobrazit v Návrháři vygenerovaný.|Ikona Dekoratéra|
|Název|Název dekoratéra.|IconDecorator|
|Poznámky|Neformální poznámky, které jsou přidruženy dekoratéra.|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|OffsetFromLine|Posun dekoratéra z řádku vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéra z tvaru vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí umístění dekoratéra.|SourceTop|

## <a name="textdecorator"></a>Objekt TextDecorator jako

|Vlastnost|Popis|Výchozí|
|--------------|-----------------|-------------|
|DefaultText|Výchozí text, který se má zobrazit.|Popisek|
|displayName|Název dekoratéra, který se má zobrazit v Návrháři vygenerovaný.|Popisek|
|Velikost písma|Velikost písma pro text, který se zobrazí v dekoratéra.|8|
|FontStyle|Písmo pro text, který se zobrazí v dekoratéra.|Regulární|
|Název|Název dekoratéra.|Popisek|
|Poznámky|Neformální poznámky, které jsou přidruženy dekoratéra.|\<žádné >|
|HorizontalOffset|Vodorovný posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|VerticalOffset|Svislý posun vzhledem k výchozí umístění dekoratéra, v palcích. (Na tvary pouze.)|0|
|OffsetFromLine|Posun dekoratéra z řádku vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|OffsetFromShape|Posun dekoratéra z tvaru vzhledem ke své výchozí pozici v palcích. (Na konektory pouze.)|0|
|Pozice|Výchozí umístění dekoratéra.|TargetBottom|

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)