---
title: "Vlastnosti Dekoratéry | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, decorators
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: "23"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 74e58042c5bcd2aa4883b3e8bb0fc484a59237ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)