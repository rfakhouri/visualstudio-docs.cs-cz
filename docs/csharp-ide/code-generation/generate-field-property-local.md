---
title: "Generovat pole, vlastnost nebo místní – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7304ad001b5e5c26594c147f4ffc416c9ee539c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="generate-a-field-property-or-local-in-c"></a>Generovat pole, vlastnost nebo místní v jazyce C# #
**Co:** umožňuje okamžitě generování kódu pro dříve nedeklarované pole, vlastnost nebo místní. 

**Kdy:** zavést nové pole, vlastnost nebo místní během psaní a chcete správně, automaticky deklarovat.  

**Důvod:** pole, vlastnost nebo místní může deklarovat před použitím, ale tato funkce bude generovat deklaraci a zadejte automaticky. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili pole, místní nebo vlastnost, která ještě neexistuje.

   ![Zvýrazněný kód](media/field_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **generovat pole nebo vlastnost nebo místní** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **generovat pole nebo vlastnost nebo místní** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu pole nebo vlastnost nebo místní](media/field_preview.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Pole, vlastnost nebo místní bude automaticky vytvořen s typem odvodit z jeho použití.

   ![Generování výsledků pole nebo vlastnost nebo místní](media/field_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Zobrazení náhledu změn](../../ide/preview-changes.md) 
