---
title: Refaktorovat pole na vlastnost v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: b3bb30e262374324952e38cf8b783a96ff6b3f9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="encapsulate-a-field-refactoring"></a>Zapouzdření pole refaktoring

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje zapnout pole do vlastnosti a aktualizovat všechny použití tohoto pole použití nově vytvořený vlastnosti.

**Kdy:** chcete přesunout pole do vlastnosti a aktualizujte všechny odkazy na toto pole.

**Důvod:** chcete poskytnout přístup ostatní třídy pole, ale nechcete, aby se tyto třídy umožňuje mít přímý přístup.  Nástrojem pro zabalení pole ve vlastnosti, můžete napsat kód, můžete ověřit hodnoty nejsou přiřazeny, např.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text do název pole, která má být zapouzdřena:

   - C#:

    ![Zvýrazněný - C#](media/encapsulate-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný - jazyka Visual Basic](media/encapsulate-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl + R**, pak **Ctrl + E**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     - Stiskněte klávesu **Ctrl**+**.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte buď **Encapsulate pole** položku z okna náhledu – místní nabídka.
   - **Myš**
     - Vyberte **Upravit > Refaktorovat > pro zapouzdření polí**.
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte buď **Encapsulate pole** položku z okna náhledu – místní nabídka.

   Výběr | Popis
   --------- | -----------
   **Pro zapouzdření polí (a pomocí vlastnosti)** | Zapouzdří pole s vlastností a aktualizuje všechny použití pole, které chcete použít vlastnost generovaného
   **Pro zapouzdření polí (ale stále můžete do pole)** | Zapouzdří pole s vlastností, ale nechá nezměněný všechny použití pole

   Vlastnost se vytvoří a odkazy na pole jsou aktualizovány, pokud je vybrána.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v automaticky otevíraném okně [zobrazíte co výsledkem bude](../../ide/preview-changes.md) před potvrzením k němu.

   - C#:

    ![Zapouzdření vlastnosti result - C#](media/encapsulate-result-cs.png)

   - Visual Basic:

    ![Zapouzdření vlastnosti result - jazyka Visual Basic](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)