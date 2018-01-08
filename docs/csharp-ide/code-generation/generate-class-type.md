---
title: "Generovat třídy nebo typu – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vsl.GenerateFromUsage
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: c72b9e898bd150e0d4ec1cc6a7a91d1eb7e6b7a8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-class-or-type-in-c"></a>Generovat třídu nebo typ v jazyce C# #
**Co:** umožňuje okamžitě generování kódu pro třídu nebo typu. 

**Kdy:** zavést nové třídy nebo typu a chcete správně, automaticky deklarovat.  

**Důvod:** může deklarovat třídu nebo typ před použitím, ale tato funkce bude generovat třídy nebo zadejte automaticky. 

**Postupy:**

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili třídu, která ještě neexistuje.

   ![Zvýrazněný kód](media/class_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte jednu z možností z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte jednu z možností z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu – třída](media/class_preview.png)

   Výběr | Popis
   --- | ---
   Generovat třída*TypeName*' v nový soubor | Vytvoří třídu s názvem *TypeName* do souboru s názvem *TypeName*.cs/VB
   Generovat třída*TypeName*. | Vytvoří třídu s názvem *TypeName* v aktuální soubor.
   Generovat vnořené třídy*TypeName*. | Vytvoří třídu s názvem *TypeName* vnořit do aktuální třídy.
   Vytvořit nový typ... | Vytvoří nové třídě nebo struktuře se všechny vlastnosti, které zadáte.

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Pokud jste vybrali **vygenerovat nový typ...**  položky, dialogové okno objeví se umožňující provést některé další akce.

   ![Vygenerovat typ](media/class_newtype.png)

   Výběr | Popis
   --- | ---
   Access | Nastavte typ tak, aby měl *výchozí*, *interní* nebo *veřejné* přístup.
   Typ | To je možné nastavit jako *třída* nebo *struktura*.
   Název | To nelze změnit a bude mít název, který jste již zadali.
   Projekt | Pokud jsou v řešení pro více projektů, můžete místo třída nebo struktura TTL.
   Název souboru | Můžete vytvořit nový soubor nebo typu můžete přidat do existujícího souboru.

1. Třída nebo struktura bude automaticky vytvořen s konstruktorem odvodit z jeho využití.

   ![Generování výsledků – třída](media/class_result.png)

## <a name="see-also"></a>Viz také  
[Generování kódu (C#)](../code-generation-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)