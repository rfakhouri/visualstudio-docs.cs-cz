---
title: "Implementace rozhraní – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e0b8df77e82ada8197b89fcdf451e4234a43669f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implement-an-interface-in-c"></a>Implementace rozhraní v jazyce C# #
**Co:** umožňuje okamžitě generování kódu potřebnou k implementaci rozhraní. 

**Kdy:** chcete použít dědění z rozhraní.  

**Důvod:** může ručně implementovat všechny rozhraní jeden po druhém, ale tato funkce bude automaticky generovat všechny podpisy metoda. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující mít odkazuje rozhraní, ale ještě implementována všech požadovaných členů.

   ![Zvýrazněný kód](media/interface_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **implementovat rozhraní (explicitně)** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **implementovat rozhraní (explicitně)** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Implementace třídy preview](media/interface_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.
   >
   >Kromě toho můžete použít **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna náhledu k vytvoření podpisy správné metody napříč více třídy, které implementují rozhraní.

1. Podpisy metoda v rozhraní bude automaticky vytvořený, připraveno k implementaci.

   ![Implementace výsledek – třída](media/interface_result.png)

   >[!TIP]
   >Použití **implementovat rozhraní explicitně** možnost Adresa každý generované metodu s názvem rozhraní tak, aby se zabránilo kolize názvů.
   >
   >![Implementovat rozhraní explicitně dojít.](media/interface_explicitresult.png); 

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)  
