---
title: Refaktorovat podpis metody v jazyce Visual Basic | Microsoft Docs
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: daee27902bd602dfe1d67533ce45f42f44a3aba4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="change-a-method-signature-in-visual-basic"></a>Změnit podpis metody v jazyce Visual Basic

**Co:** umožňuje odebrat nebo změnit pořadí parametrů metody.

**Kdy:** chcete přesunout nebo odebrat parametru metody, která je aktuálně používána v různých umístěních.  

**Důvod:** může ručně odebrat a změnit pořadí parametrů a pak najít všechna volání této metody a změnit je jeden po druhém, ale které může vést k chybám.  Tento nástroj refaktoringu automaticky provede úlohu.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název metody k úpravě nebo jeden z jeho použití:

   ![Zvýrazněný kód](media/changesignature-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **kombinaci kláves Ctrl + V**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > pro odebrání parametrů**.
     * Vyberte **Upravit > Refaktorovat > přeskupení parametrů**.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.

1. V **změnit podpis** dialogové okno, která se objeví, změníte podpis metody můžete pomocí tlačítek na pravé straně:

   ![Dialogové okno změnit podpis](media/changesignature-dialog-vb.png)

   | Tlačítko | Popis
   | ------ | ---
   | **Nahoru/dolů** | Přesunout vybraný parametr nahoru a dolů v seznamu
   | **Odebrat**  | Odeberte parametr vybraný ze seznamu
   | **Obnovení** | Obnovení vybraný, přeškrtnutý parametru do seznamu

   > [!TIP]
   > Použití [ **zobrazení náhledu změn odkaz** ](../../ide/preview-changes.md) zaškrtávací políčko, pokud chcete zobrazit, co výsledkem bude před potvrzením k němu.

1. Když skončíte, stiskněte **OK** tlačítko provést změny.

   ![Podpis výsledek změny](media/changesignature-result-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)