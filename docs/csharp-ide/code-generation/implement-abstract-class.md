---
title: "Implementace abstraktní třídy – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: ff462a62bfd7fe687f2b0d35f365e76468a7e0e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="implement-an-abstract-class-in-c"></a>Implementace abstraktní třídy v jazyce C# #
**Co:** umožňuje okamžitě generování kódu potřebnou k implementaci abstraktní třídu. 

**Kdy:** chcete použít dědění z abstraktní třídy.  

**Důvod:** ručně může implementovat všechny abstraktní členy jeden po druhém, ale tato funkce bude automaticky generovat všechny podpisy metoda. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující mít dědí z abstraktní třídy, ale ještě implementována všech požadovaných členů.

   ![Zvýrazněný kód](media/abstract_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **abstraktní třída implementace** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **abstraktní třída implementace** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Implementace třídy preview](media/abstract_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.
   >
   >Kromě toho můžete použít **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna náhledu k vytvoření podpisy správné metody napříč více třídy, které dědí z abstraktní třídy.

1. Podpisy abstraktní metodu bude automaticky vytvořený, připraveno k implementaci.

   ![Implementace výsledek – třída](media/abstract_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)
