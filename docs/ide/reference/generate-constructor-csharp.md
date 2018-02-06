---
title: "Generovat konstruktor – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: b6e73b3b012547e98934bbcd76d1ee2eb0f3324d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-constructor-in-c"></a>Generovat konstruktor v jazyce C# #
**Co:** umožňuje okamžitě generování kódu pro nový konstruktor na třídu. 

**Kdy:** zavést nové konstruktor a chcete správně deklarujte ji automaticky, nebo upravit existující konstruktor. 

**Důvod:** konstruktor může deklarovat před použitím, ale tato funkce bude generovat, s odpovídající parametry, automaticky. Kromě toho úpravy existující konstruktor vyžadují aktualizaci všech callsites, pokud je automaticky aktualizovat pomocí této funkce.

**Postupy:** generovat konstruktor několika způsoby:
- [Generovat konstruktor a vyberte členy](#pick)
- [Generování konstruktor z vybraného pole](#selection)
- [Generování konstruktor z nové využití](#usage)
- [Přidejte parametr existující konstruktoru](#addparameter)
- [Vytvoření a inicializace pole nebo vlastnost z parametr konstruktoru](#create)

## <a id = "pick"></a>Generovat konstruktor a vyberte členy
1. Umístěte ukazatel myši v jakékoli prázdný řádek v třídě:

   ![Kurzor se nachází v prázdný řádek](media/constructor1-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **generování konstruktor...**  z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **generování konstruktor...**  z okna náhledu – místní nabídka.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí na levém okraji, pokud již text kurzor na prázdný řádek ve třídě.

   ![Vytvoření náhledu – konstruktor](media/constructor1-preview-cs.png)

1. Dialogové okno se zobrazí, abyste mohli vybrat členy, které chcete použít jako parametry konstruktor a také jejich pořadí (s nahoru a dolů). Stiskněte klávesu **Ok** uložte provedené změny.
  
   ![Dialogové okno Vybrat členy](media/constructor1-dialog-cs.png)

   >[!TIP] 
   >Můžete zkontrolovat **přidat kontroly hodnoty null** zaškrtávací políčko k automatickému generování kontroly hodnoty null pro konstruktor parametry.

1. V konstruktoru bude vytvořen s vybraných parametrů v zadaném pořadí.
   ![Generování výsledků – konstruktor](media/constructor1-result-cs.png)

## <a id="selection"></a>Generování konstruktor z vybraného pole
1. Zvýrazněte členy chcete mít ve vaší generovaného konstruktor: ![zvýrazněte členy](media/constructor2-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **generování konstruktor 'TypeName(...).**  z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **generování konstruktor 'TypeName(...).**  z okna náhledu – místní nabídka.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s výběrem.

     ![Vytvoření náhledu – konstruktor](media/constructor2-preview-cs.png)

1. V konstruktoru bude vytvořen s vybraných parametrů.
     ![Generování výsledků – konstruktor](media/constructor2-result-cs.png)

## <a id="usage"></a>Generování konstruktor z nové využití
1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili konstruktor, který ještě neexistuje.

   ![Zvýrazněný kód](media/constructor-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **konstruktor generovat v '*TypeName*'** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **konstruktor generovat v '*TypeName*'** z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Vytvoření náhledu – konstruktor](media/constructor-preview-cs.png)

   >[!TIP]
   >Použití [ **zobrazení náhledu změn** ](../../ide/preview-changes.md) odkaz v dolní části okna náhledu zobrazíte všechny změny provedené před provedením váš výběr.

1. Konstruktoru bude automaticky vytvořen s parametry odvodit z jeho použití.

   ![Generování výsledků – konstruktor](media/constructor-result-cs.png)

## <a id="addparameter"></a>Přidejte parametr existující konstruktoru
1. Přidání parametru k existující instanci objektu.

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili konstruktor, který ještě neexistuje.
    
    ![Generovat zvýraznění – konstruktor](media/constructor4-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **přidáte parametr 'TypeName(...).**  z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **přidáte parametr 'TypeName(...).**  z okna náhledu – místní nabídka.
     * Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu – konstruktor](media/constructor4-preview-cs.png)

1. Parametr automaticky přidá, s příslušným typem odvodit z jeho použití.
   
   ![Generování výsledků – konstruktor](media/constructor4-result-cs.png)

## <a id="create"></a>Vytvoření a inicializace pole nebo vlastnost z parametr konstruktoru
1. Z existující konstruktoru přidejte parametr:

   ![Generovat zvýraznění – konstruktor](media/constructor5-highlight-cs.png)

1. Umístěte kurzor do nově přidaného parametru.

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **vytvoření a inicializace vlastnost 'YourProperty'** nebo **vytvoření a inicializace pole 'YourField'** z Místní okno náhledu.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **vytvoření a inicializace vlastnost 'YourProperty'** nebo **vytvoření a inicializace pole 'YourField'**z okna náhledu – místní nabídka.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s parametrem přidané.

   ![Vytvoření náhledu – konstruktor](media/constructor5-preview-cs.png)

1. Pole nebo vlastnost, bude vytvořen a automaticky s názvem tak, aby odpovídaly vaší typy.

   ![Generování výsledků – konstruktor](media/constructor5-result-cs.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)