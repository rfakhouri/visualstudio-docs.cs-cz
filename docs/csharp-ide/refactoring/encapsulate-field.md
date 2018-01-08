---
title: "Refaktoring pro zapouzdření polí - (C#) | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 39a9ed11-363f-4dda-af3b-0affe6db1d42
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 59b71a0716415dcedeab9954486ef27e0fc438d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="encapsulate-a-field-in-c"></a>Zapouzdření pole v jazyce C# #
**Co:** umožňuje zapnout pole do vlastnosti a aktualizovat všechny použití tohoto pole použití nově vytvořený vlastnosti.

**Kdy:** chcete přesunout pole do vlastnosti a aktualizujte všechny odkazy na toto pole.  

**Důvod:** chcete poskytnout přístup ostatní třídy pole, ale nechcete, aby se tyto třídy umožňuje mít přímý přístup.  Nástrojem pro zabalení pole ve vlastnosti, můžete napsat kód, můžete ověřit hodnoty nejsou přiřazeny, např.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název pole, která má být zapouzdřena:

   ![Zvýrazněný kód](media/encapsulate_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **Ctrl + E**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte buď **Encapsulate pole** položku z okna náhledu – místní nabídka.
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > pro zapouzdření polí**.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte buď **Encapsulate pole** položku z okna náhledu – místní nabídka.

   Výběr | Popis
   --------- | -----------
   **Pro zapouzdření polí (a pomocí vlastnosti)** | Zapouzdří pole s vlastností a aktualizuje všechny použití pole, které chcete použít vlastnost generovaného
   **Pro zapouzdření polí (ale stále můžete do pole)** | Zapouzdří pole s vlastností, ale nechá nezměněný všechny použití pole

   Vlastnost se okamžitě vytvoří a odkazy na pole bude aktualizován, pokud vybraný.

   > [!TIP]
   > Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v automaticky otevíraném okně, které chcete zobrazit, co výsledkem bude před potvrzením k němu.

   ![Zapouzdření vlastnost výsledek](media/encapsulate_result.png)

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)