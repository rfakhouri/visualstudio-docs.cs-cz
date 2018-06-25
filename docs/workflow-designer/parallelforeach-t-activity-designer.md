---
title: Návrhář postupu provádění - ParallelForEach&lt;T&gt; Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53b8a8790cfa4f4e1f962fa5e6ce82b62781430f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756903"
---
# <a name="parallelforeach-activity-designer"></a>Návrhář aktivity ParallelForEach

<xref:System.Activities.Statements.ParallelForEach%601> Aktivity zobrazí prvky kolekce a spouští příkazu embedded pro každý prvek kolekce souběžně, což je asynchronně ve stejném vlákně. Pomocí této aktivity toku řízení místo <xref:System.Activities.Statements.Sequence> aktivitu, pokud se očekává, že podřízené aktivity této aktivity přejděte nečinnosti.

<xref:System.Activities.Statements.ParallelForEach%601> Aktivita má <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> vlastnost, která obsahuje jméno uživatele zadaný výraz jazyka Visual Basic. <xref:System.Activities.Statements.ParallelForEach%601> Aktivita vyhodnotí tuto vlastnost po dokončení každé větve. Pokud je vyhodnocen jako **true**, pak se <xref:System.Activities.Statements.ParallelForEach%601> bez provádění ostatní větve zůstanou dokončení aktivity. Pokud <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> není vyhodnocen **true**, pak se <xref:System.Activities.Statements.ParallelForEach%601> dokončení aktivity, když byly dokončeny všechny jeho podřízené aktivity.

## <a name="the-parallelforeacht-activity"></a>ParallelForEach < T\> aktivity

<xref:System.Activities.Statements.ParallelForEach%601> Vytvoří výčet jeho hodnoty a plány <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> pro každou hodnotu, která se zobrazí na. Pouze plány <xref:System.Activities.Statements.ParallelForEach%601.Body%2A>. Jak text provede závisí na tom, zda <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> přejde nečinnosti.

Pokud <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> nepřekračuje nečinný, se provede v obráceném pořadí protože naplánované aktivity jsou zpracovávány jako zásobník, nejprve provede poslední naplánovanou činností. Například, pokud máte kolekci {1,2,3,4}v <xref:System.Activities.Statements.ParallelForEach%601> a použít **WriteLine** jako text zprávy pro zápis hodnoty. Máte 4, 3, 2, 1 vytištěna v konzole. Důvodem je, že **WriteLine** nepřekračuje nečinnosti, po 4 **WriteLine** tu naplánované aktivity, jejich spouštěných pomocí chování zásobníku (první v poslední na více systémů).

Ale pokud máte aktivity ve <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> , můžete přejít nečinnosti, jako je <xref:System.ServiceModel.Activities.Receive> aktivity nebo <xref:System.Activities.Statements.Delay> aktivity. Je nutné počkat na jejich dokončení. <xref:System.Activities.Statements.ParallelForEach%601> Přejde na další naplánované aktivity textu a pokuste se ho provést. Pokud aktivity, přejde nečinnosti <xref:System.Activities.Statements.ParallelForEach%601> přesune na znovu na další aktivitu textu.

### <a name="using-the-parallelforeacht-activity-designer"></a>Pomocí ParallelForEach\<T > Návrhář aktivity

Přístup **ParallelForEach\<T >** Návrhář aktivity v **tok řízení** kategorii **sada nástrojů**.

**ParallelForEach\<T >** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na návrháře aktivit jsou obvykle umístěny, pro Příklad, uvnitř **pořadí** Návrhář aktivity. Po vyřazení ho do návrháře pracovních postupů, vytvoří <xref:System.Activities.Statements.ParallelForEach%601> aktivity, který ve výchozím nastavení obsahuje <xref:System.Activities.Activity.DisplayName%2A> z **ParallelForEach < Int32\>.**

### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach < T\> vlastnosti v Návrháři pracovních postupů

V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.ParallelForEach%601> vlastnosti aktivity a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný Zobrazovaný název Návrhář aktivity v hlavičce. Výchozí hodnota je **ParallelForEach\<Int32 >**. Hodnota může volitelně upravena v **vlastnosti** mřížky nebo přímo v hlavičce Návrhář aktivity.|
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|Aktivita provést pro každou položku v kolekci. Chcete-li přidat <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> aktivity, vyřaďte aktivitu z panelu nástrojů do **textu** pole na **ParallelForEach\<T >** Návrhář aktivity s text nápovědy "Aktivity Sem přetáhněte".|
|**TypeArgument**|Hodnota TRUE|Typ položky v <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> kolekce určeného obecný parametr *T*. Ve výchozím nastavení **TypeArgument** je nastaven na **Int32**. Chcete-li změnit typ T v **ParallelForEach < T\>**  Návrhář aktivity, změňte hodnotu **TypeArgument** – pole se seznamem v tabulce vlastností.|
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|Hodnota TRUE|Kolekce položek, které mají iterace. Chcete-li nastavit <xref:System.Activities.Statements.ParallelForEach%601.Values%2A>, zadejte výraz jazyka Visual Basic v **hodnoty** pole na **ForEach < T\>**  Návrhář aktivity do pole s textem pomocný parametr "Zadejte výraz VB" nebo v  **Hodnoty** pole na **vlastnosti** okno.|
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||Vyhodnocení po každé iteraci dokončení. Pokud je vyhodnocen jako true, pak plánované čekající na vyřízení došlo ke zrušení iterací. Pokud není tato vlastnost nastavena, všechny naplánované příkazy spustit až do dokončení.|

Ve výchozím nastavení iterace smyčky názvem položky. Můžete změnit název proměnné iterator v **ForEach** pole **ParallelForEach\<T >** Návrhář aktivity. Iterator smyčky lze použít ve výrazech v podřízených prvků <xref:System.Activities.Statements.ParallelForEach%601> aktivity.

## <a name="see-also"></a>Viz také:

- [Pořadí](../workflow-designer/sequence-activity-designer.md)
- [Paralelní](../workflow-designer/parallel-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)