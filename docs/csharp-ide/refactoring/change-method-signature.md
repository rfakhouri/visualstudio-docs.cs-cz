---
title: "Podpis metody změnu - refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: b4f45f9d-9c8f-46ae-99f7-7705c6d90b6e
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: csharp
ms.openlocfilehash: 9ed72704c37fcfc5d0c48ba17937f5b06097ce0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="change-a-method-signature-in-c"></a>Změnit podpis metody v jazyce C# #
**Co:** umožňuje odebrat nebo změnit pořadí parametrů metody.

**Kdy:** chcete přesunout nebo odebrat parametru metody, která je aktuálně používána v různých umístěních.  

**Důvod:** může ručně odebrat a změnit pořadí parametrů a pak najít všechna volání této metody a změnit je jeden po druhém, ale které může vést k chybám.  Tento nástroj refaktoringu automaticky provede úlohu.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název metody k úpravě nebo jeden z jeho použití:

   ![Zvýrazněný kód](media/changesignature_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **kombinaci kláves Ctrl + V**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > pro odebrání parametrů**.
     * Vyberte **Upravit > Refaktorovat > přeskupení parametrů**.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.

1. V **změnit podpis** dialogové okno, která se objeví, změníte podpis metody můžete pomocí tlačítek na pravé straně:

   ![Dialogové okno změnit podpis](media/changesignature_dialog.png)

   | Tlačítko | Popis
   | ------ | ---
   | **Nahoru/dolů** | Přesunout vybraný parametr nahoru a dolů v seznamu
   | **Odebrat**  | Odeberte parametr vybraný ze seznamu
   | **Obnovení** | Obnovení vybraný, přeškrtnutý parametru do seznamu

   > [!TIP]
   > Použití [ **zobrazení náhledu změn odkaz** ](../../ide/preview-changes.md) zaškrtávací políčko, pokud chcete zobrazit, co výsledkem bude před potvrzením k němu.

1. Když skončíte, stiskněte **OK** tlačítko provést změny.

   ![Podpis výsledek změny](media/changesignature_result.png)

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Zobrazení náhledu změn](../../ide/preview-changes.md)