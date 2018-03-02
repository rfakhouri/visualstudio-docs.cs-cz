---
title: "Refaktorovat podpis metody v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: c181eb27ccdbc2f1efb7294e1610a6055245241c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="change-a-method-signature-refactoring"></a>Změnit refaktoring podpis – metoda

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje odebrat nebo změnit pořadí parametrů metody.

**Kdy:** chcete přesunout nebo odebrat parametru metody, která je aktuálně používána v různých umístěních.

**Důvod:** může ručně odebrat a změnit pořadí parametrů a pak najít všechna volání této metody a změnit je jeden po druhém, ale které může vést k chybám.  Tento nástroj refaktoringu automaticky provede úlohu.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text do název metody k úpravě nebo jeden z jeho použití:

   - C#:

    ![Zvýrazněný kód C#](media/changesignature-highlight-cs.png)

   - VB:

    ![Zvýrazněný kód jazyka Visual Basic](media/changesignature-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl + R**, pak **kombinaci kláves Ctrl + V**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.
   - **Myš**
     - Vyberte **Upravit > Refaktorovat > pro odebrání parametrů**.
     - Vyberte **Upravit > Refaktorovat > přeskupení parametrů**.
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **změnu podpis** z okna náhledu – místní nabídka.

1. V **změnit podpis** dialogové okno, která se objeví, změníte podpis metody můžete pomocí tlačítek na pravé straně:

   ![Dialogové okno změnit podpis](media/changesignature-dialog-cs.png)

   | Tlačítko | Popis
   | ------ | ---
   | **Nahoru/dolů** | Přesunout vybraný parametr nahoru a dolů v seznamu
   | **Odebrat**  | Odeberte parametr vybraný ze seznamu
   | **Obnovení** | Obnovení vybraný, přeškrtnutý parametru do seznamu

   > [!TIP]
   > Použití **zobrazení náhledu změn odkaz** zaškrtávacího políčka [najdete v části co výsledkem bude](../../ide/preview-changes.md) před potvrzením k němu.

1. Když skončíte, stiskněte **OK** tlačítko provést změny.

   - C#:

    ![Změnit podpis result - C#](media/changesignature-result-cs.png)

   - Visual Basic:

    ![Změnit podpis result - jazyka Visual Basic](media/changesignature-result-vb.png)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)