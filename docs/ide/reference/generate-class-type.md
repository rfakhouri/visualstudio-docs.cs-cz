---
title: Generovat třídy nebo typu v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vsl.GenerateFromUsage
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 030c4736eea942432175d0320d020a6b45888517
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="generate-a-class-or-type-in-visual-studio"></a>Generovat třídy nebo typu v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu pro třídu nebo typu.

**Kdy:** zavést nové třídy nebo typu a chcete správně, automaticky deklarovat.

**Důvod:** může deklarovat třídu nebo typ před použitím, ale tato funkce bude generovat třídy nebo zadejte automaticky.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází červenou vlnovkou. Červenou vlnovkou Určuje třídu, která ještě neexistuje.

   - C#:

    ![Zvýrazněný kód C#](media/class-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/class-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

    ![Vytvoření náhledu – třída](media/class-preview-cs.png)

1. Z rozevírací nabídky vyberte jednu z možností:

   - Generovat třída*TypeName*' v nový soubor&mdash;vytvoří třídu s názvem *TypeName* do souboru s názvem *TypeName*.cs/VB
   - Generovat třída*TypeName*'&mdash;vytvoří třídu s názvem *TypeName* v aktuální soubor.
   - Generovat vnořené třídy*TypeName*'&mdash;vytvoří třídu s názvem *TypeName* vnořit do aktuální třídy.
   - Vytvořit nový typ... &mdash;Vytvoří nové třídě nebo struktuře se všechny vlastnosti, které zadáte.

   > [!TIP]
   > Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.

1. Pokud jste vybrali **vygenerovat nový typ...**  položku **generovat typ** otevře se dialogové okno. Konfigurovat usnadnění, typ a umístění nového typu.

   ![Vygenerovat typ](media/class-newtype-cs.png)

   Výběr | Popis
   --- | ---
   Access | Nastavte typ tak, aby měl *výchozí*, *interní* nebo *veřejné* přístup.
   Typ | To je možné nastavit jako *třída* nebo *struktura*.
   Název | To nelze změnit a bude mít název, který jste již zadali.
   Projekt | Pokud jsou v řešení pro více projektů, můžete místo třída nebo struktura TTL.
   Název souboru | Můžete vytvořit nový soubor nebo typu můžete přidat do existujícího souboru.

Třídě nebo struktuře se vytvoří. Pro jazyk C# se také vytvoří konstruktor.

- C#

   ![Generování výsledků třída C#](media/class-result-cs.png)

- Visual Basic

   ![Generování výsledků třídy jazyka Visual Basic](media/class-result-vb.png)

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)