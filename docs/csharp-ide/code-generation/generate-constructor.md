---
title: "Generovat konstruktor – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 31b0a187e0640a94d9401a1e20fd03d81ff5b920
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="generate-a-constructor-in-c"></a>Generovat konstruktor v jazyce C# #
**Co:** umožňuje okamžitě generování kódu pro nový konstruktor na třídu. 

**Kdy:** zavést nový konstruktor a chcete správně, automaticky deklarovat.  

**Důvod:** konstruktor může deklarovat před použitím, ale tato funkce bude generovat, s odpovídající parametry, automaticky. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili konstruktor, který ještě neexistuje.

   ![Zvýrazněný kód](media/constructor_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte  **konstruktor generovat v '*TypeName*' ** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte  **konstruktor generovat v '*TypeName*' ** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu – konstruktor](media/constructor_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Konstruktoru bude automaticky vytvořen s parametry odvodit z jeho použití.

   ![Generování výsledků – konstruktor](media/constructor_result.png)
  
## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Zobrazení náhledu změn](../../ide/preview-changes.md)