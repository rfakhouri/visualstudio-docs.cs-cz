---
title: "Generovat konstruktor – generování kódu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 891a33b74927d45434c4614dc4c5d7f1533ba4c0
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-constructor-in-visual-basic"></a>Generovat konstruktor v jazyce Visual Basic
**Co:** umožňuje okamžitě generování kódu pro nový konstruktor na třídu. 

**Kdy:** zavést nový konstruktor a chcete správně, automaticky deklarovat.  

**Důvod:** konstruktor může deklarovat před použitím, ale tato funkce bude generovat, s odpovídající parametry, automaticky. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili konstruktor, který ještě neexistuje.

   ![Zvýrazněný kód](media/constructor-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **konstruktor generovat v '*TypeName*'** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **konstruktor generovat v '*TypeName*'** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-vb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb-vb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu – konstruktor](media/constructor-preview-vb.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Konstruktoru bude automaticky vytvořen s parametry odvodit z jeho použití.

   ![Generování výsledků – konstruktor](media/constructor-result-vb.png)
 
## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)