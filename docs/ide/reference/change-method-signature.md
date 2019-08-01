---
title: Změna podpisu metody
description: Odeberte nebo změňte pořadí parametrů metody. Klikněte pravým tlačítkem na metodu, vyberte rychlé akce a refaktoring a vyberte změnit signaturu.
ms.date: 01/26/2018
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 97c03c798732b5d722b2dc49f3ec7ffa490b4f06
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/01/2019
ms.locfileid: "68711266"
---
# <a name="change-a-method-signature-refactoring"></a>Změna podpisu metody refaktoring

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje odebrat nebo změnit pořadí parametrů metody.

**Kdy:** Chcete přesunout nebo odebrat parametr metody, který je aktuálně používán v různých umístěních.

**Proč:** Můžete ručně odebrat a změnit pořadí parametrů a pak vyhledat všechna volání této metody a změnit je po jednom, ale to může vést k chybám.  Tento refaktoring nástroj automaticky provede úlohu.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text mezi název metody, která upravit, nebo jedno z jeho použití:

   - C#:

       ![Zvýrazněný kód jazyka C#](media/changesignature-highlight-cs.png)

   - VB:

       ![Zvýrazněný kód jazyka Visual Basic](media/changesignature-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl + R**, pak **Ctrl + V**.  (Všimněte si, že klávesová zkratka může být jiný platformě, na který profil vyberete.)
      - Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky a vybereme **změnit signaturu** z automaticky otevíraného okna okno náhledu.
   - **Myši**
      - Vyberte **Upravit > Refaktorovat > pro odebrání parametrů**.
      - Vyberte **Upravit > Refaktorovat > přeskupení parametrů**.
      - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a Refaktoringy** nabídky a vybereme **změnit signaturu** z automaticky otevíraného okna okno náhledu.

3. V **změnit podpis** dialogového okna, která se otevře, můžete změnit podpis metody můžete pomocí tlačítka na pravé straně:

   ![Změnit podpis dialogového okna](media/changesignature-dialog-cs.png)

   | Tlačítko | Popis
   | ------ | ---
   | **Směrem nahoru nebo dolů** | Přesunout vybraný parametr nahoru a dolů v seznamu
   | **odebrat** | Odebrat vybraný parametr ze seznamu
   | **Obnovení** | Obnovit vybrané, přeškrtnutý parametru do seznamu

   > [!TIP]
   > Použití **náhled změn odkazu** zaškrtávací políčko a [naleznete v tématu co se bude výsledek](../../ide/preview-changes.md) před potvrzením do něj.

4. Až skončíte, stiskněte **OK** tlačítko provést změny.

   - C#:

      ![Změnit podpis výsledek-C#](media/changesignature-result-cs.png)

   - Visual Basic:

      ![Změnit podpis výsledek - jazyka Visual Basic](media/changesignature-result-vb.png)

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)