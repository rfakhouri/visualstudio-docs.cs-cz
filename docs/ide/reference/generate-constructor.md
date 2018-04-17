---
title: Generovat konstruktor v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 8ab26fd6ccc8359c2699154ae6fa5821040ce9ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="generate-a-constructor-in-visual-studio"></a>Generovat konstruktor v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu pro nový konstruktor na třídu.

**Kdy:** zavést nové konstruktor a chcete správně deklarujte ji automaticky, nebo upravit existující konstruktor.

**Důvod:** konstruktor může deklarovat před použitím, ale tato funkce bude generovat, s odpovídající parametry, automaticky. Kromě toho úpravy existující konstruktor vyžadují aktualizaci všech callsites, pokud je automaticky aktualizovat pomocí této funkce.

**Postupy:** generovat konstruktor několika způsoby:

   - [Generovat konstruktor a vyberte členy](#pick)
   - [Generování konstruktor z vybraného pole](#selection)
   - [Generování konstruktor z nové využití](#usage)
   - [Přidejte parametr existující konstruktoru](#addparameter)
   - [Vytvoření a inicializace pole nebo vlastnost z parametr konstruktoru](#create)

## <a id = "pick"></a> Generovat konstruktor a vyberte členy (C# pouze)

1. Umístěte ukazatel myši v jakékoli prázdný řádek v třídě:

   ![Kurzor se nachází v prázdný řádek](media/constructor1-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí na levém okraji, pokud již text kurzor na prázdný řádek ve třídě.

   ![Vytvoření náhledu – konstruktor](media/constructor1-preview-cs.png)

1. Vyberte **generování konstruktor...**  z rozevírací nabídky.

   **Vyberte memebers** otevře se dialogové okno.

1. Vyberte členy, které chcete zahrnout jako parametry konstruktor. Můžete pořadí pomocí nahoru a dolů šipky. Zvolte **OK**.

   ![Dialogové okno Vybrat členy](media/constructor1-dialog-cs.png)

   > [!TIP]
   > Můžete zkontrolovat **přidat kontroly hodnoty null** zaškrtávací políčko k automatickému generování kontroly hodnoty null pro konstruktor parametry.

   Konstruktor se vytvoří se zadanými parametry.

   ![Generování výsledků – konstruktor](media/constructor1-result-cs.png)

## <a id="selection"></a> Generování konstruktor z vybraného pole (C# pouze)

1. Zvýrazněte členů, které chcete mít v vaší generovaného konstruktoru:

   ![Zvýrazněte členy](media/constructor2-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s výběrem.

     ![Vytvoření náhledu – konstruktor](media/constructor2-preview-cs.png)

1. Vyberte **generování konstruktor 'TypeName(...).**  z rozevírací nabídky.

   Konstruktor je vytvořen s vybraných parametrů.

   ![Generování výsledků – konstruktor](media/constructor2-result-cs.png)

## <a id="usage"></a> Generování konstruktor z nové využití (C# a Visual Basic)

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou. Červenou vlnovkou označuje volání konstruktoru, který ještě neexistuje.

   - C#:

    ![Zvýrazněný kód C#](media/constructor-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/constructor-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu – konstruktor](media/constructor-preview-cs.png)

1. Vyberte **konstruktor generovat v '*TypeName*'** z rozevírací nabídky.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.

   Konstruktor je vytvořen s parametry odvodit z jeho použití.

   - C#:

      ![Generovat výsledek metody C#](media/constructor-result-cs.png)

   - Visual Basic:

      ![Generovat výsledek metody jazyka Visual Basic](media/constructor-result-vb.png)

## <a id="addparameter"></a> Přidejte parametr existující konstruktoru (C# pouze)

1. Přidání parametru do existujícího hovoru konstruktor.

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou označující jste použili konstruktor, který ještě neexistuje.

    ![Generovat zvýraznění – konstruktor](media/constructor4-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu – konstruktor](media/constructor4-preview-cs.png)

1. Vyberte **přidáte parametr 'TypeName(...).**  z rozevírací nabídky.

   Parametr je přidán do konstruktoru, s příslušným typem odvodit z jeho použití.

   ![Generování výsledků – konstruktor](media/constructor4-result-cs.png)

## <a id="create"></a> Vytvoření a inicializace pole nebo vlastnost z parametr konstruktoru (C# pouze)

1. Najít existující konstruktor a přidejte parametr:

   ![Generovat zvýraznění – konstruktor](media/constructor5-highlight-cs.png)

1. Umístěte kurzor do nově přidaného parametru.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s parametrem přidané.

   ![Vytvoření náhledu – konstruktor](media/constructor5-preview-cs.png)

1. Vyberte **vytvoření a inicializace vlastnost** nebo **vytvoření a inicializace pole** z rozevírací nabídky.

   Pole nebo vlastnost je deklarovaná a automaticky s názvem tak, aby odpovídaly vaší typy. Řádek kódu je také přidán k chybě při inicializaci pole nebo vlastnost v těle konstruktor.

   ![Generování výsledků – konstruktor](media/constructor5-result-cs.png)

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)