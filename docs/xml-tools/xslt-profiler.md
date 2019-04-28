---
title: Výkon XSLT
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 87387c9a-2e89-4801-ad51-83740cd6ea25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ecc5482c8519ceadfe1e6d5db7880c98b3d2ceb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62988055"
---
# <a name="the-xslt-profiler"></a>Profiler XSLT

Profiler XSLT chyb vytváří detailní zprávy XSLT výkonu, které pomůže měřit, vyhodnotit a řešit problémy související s výkonem v kódu XSLT. Profiler XSLT zahrnuje užitečných rad pro XSL a XSLT optimalizace list stylu. Pro aplikace XSLT tento požadavek maximální výkon, tento nástroj může být nezbytné.

Profiler XSLT je součástí sady Visual Studio a je k dispozici na **XML** nabídky.

![Profiler XSLT](../xml-tools/media/profile-xslt-menu.png)

> [!NOTE]
> Profiler XSLT je dostupná pouze v edici Enterprise systému Visual Studio.

## <a name="create-a-performance-report"></a>Vytvoření sestavy výkonu

1. Otevření dokumentu XSLT v sadě Visual Studio.

2. V panelu nabídky zvolte **XML** > **profilu XSLT**.

3. Zadejte vstupní dokument XML. Pokud dokument XML již není otevřen, zobrazí se výzva k zadání soubor.

   Spuštění analýzy a indikátoru průběhu zobrazí průběh v editoru. Výstup XSLT je také viditelné.

4. Po ukončení relace výkonu, zkontrolujte zprávu o výkonu k analýze výkonu XSLT.

## <a name="get-all-available-views"></a>Získání všech dostupných zobrazení

1. Klikněte na **aktuální zobrazení** rozevíracího seznamu zobrazíte všechny dostupné zobrazení.

2. Vyberte **souhrnné zobrazení** možnost **aktuální zobrazení** rozevíracího seznamu. Ve výchozím nastavení, zobrazí se sestava výkonu v **souhrnné zobrazení**. Toto zobrazení je výchozím bodem k určení problémů s výkonem pomocí XSLT dokumentů. **Souhrnné zobrazení** uvádí těchto datových bodů:

   - Nejvíce volané funkce

   - Funkce s většinou jednotlivé práce

   - Funkce beroucí nejdéle ke spuštění

   Ve výchozím nastavení, existují tři sloupce pro každý datový bod: název funkce, počet volání v absolutní hodnota a procentuální hodnotu s názvem funkce, která se celkový počet funkce volání. Z každého datového bodu **souhrnné zobrazení**, můžete přejít na podrobnější zobrazení kliknutím pravým tlačítkem myši na funkci datových bodů.

3. Vyberte **zobrazení funkce** možnost **aktuální zobrazení** rozevíracího seznamu. **Zobrazení funkce** seznam funkcí, volá se během profilace. Data lze seřadit klepnutím na název sloupce. Sloupce zobrazí ve výchozím nastavení jsou:

    - **Název funkce**

    - **Uplynulý celkový čas**

    - **Uplynulý výhradní čas**

    - **Celkový čas aplikace**

    - **Výhradní čas aplikace**

    - **Počet volání**

   Všechny sloupce času jsou zobrazeny v absolutní hodnoty a procenta. Termín **exkluzivní** odkazuje na celkový čas strávený provádění bez času spotřebovaného přidělenými jiné funkce volá se během provádění této funkce funkce.

   Termín **celkový čas** odkazuje na celkovou dobu funkce stráven spouštěním, včetně spuštění všech funkcí názvem a určuje, zda některé z těchto volat funkce volá jiné funkce.

## <a name="select-callercallee-view"></a>Vyberte zobrazení volající/volaný

Vyberte **volající/volaný** zobrazit **aktuální zobrazení** rozevíracího seznamu. **Volající/volaný** zobrazení má následující tři samostatné části:

- **Funkce, které volaly**: Všechny funkce, které volaly konkrétní funkce jsou uvedené na horní část zobrazení.

- **Aktuální funkce**: Konkrétní funkce, která byla volána je uveden v prostřední části zobrazení.

- **Funkce, které byly volány**: Všechny funkce, které byly volány konkrétní funkce jsou uvedeny v dolní části zobrazení.

Pokud funkci s názvem `SyncToNavigator` se zobrazí v prostřední části zobrazíte všechny funkce, které volá `SyncToNavigator` funkce se zobrazí v horní části zobrazení a všechny funkce, které byly volány `SyncToNavigator` se zobrazí v dolní části zobrazení.

- Funkce ve střední části zobrazení můžete změnit poklepáním na některé z funkcí uvedených v dalších částech dvě zobrazení. Zobrazení se pak aktualizuje tak, aby odrážely změny automaticky.

- Data můžete také řadit kliknutím názvy sloupců.

## <a name="select-call-tree-view"></a>Vyberte zobrazení stromu volání

- Vyberte **zobrazení stromu volání** v **aktuální zobrazení** rozevíracího seznamu. Toto zobrazení je stromové zobrazení provádění programu.

   **Zobrazení stromu volání** ukazuje kořen stromu jako název procesu. Funkce jsou uzly stromu. Toto zobrazení můžete přejít k podrobnostem konkrétní volání trasování a analyzovat trasování, které mají největší dopad na výkon. Zobrazení se podobá **zobrazení zásobníku volání** dostupný během ladění. Kromě sloupce v **zobrazení funkce**v **zobrazení stromu volání**, existuje další sloupec, který se zobrazí **název modulu**.

- Vyberte **značky** v **aktuální zobrazení** rozevíracího seznamu.

   Profiler XSLT existuje značky, které se zobrazí v datovém proudu kolekce s přidružené komentář. Značky jsou místa v kódu, které mají čítače. Pokud dáte Profiler XSLT se získat čítače výkonu XSLT, získat čítače shromažďují pokaždé, když se provede jednu z těchto značek. Data se zobrazí v tabulce obsahující **ID značky**, **název značky** (**spustit Program**, **ukončit Program**) a  **Časové razítko**. Značky se agregují a zobrazují se v chronologickém pořadí v **zobrazení značky** sestavy výkonu.

## <a name="select-modules-in-the-current-view"></a>Vyberte moduly v aktuálním zobrazení

- Vyberte **moduly** v **aktuální zobrazení** rozevíracího seznamu.

   Zobrazení modulů je plochý seznam všech funkcí, které agregují na úrovni modulu. Rozbalit nebo sbalit název modulu pro zobrazení nebo zobrazení dat výkonu modulu zavřít. Data lze seřadit klepnutím na název sloupce. Ve výchozím nastavení, jsou hodnoty absolutní a procentuální čísla **uplynulý celkový čas**, **uplynulý výhradní čas**, **celkový čas aplikace**, **Výhradní čas aplikace**, a **počet volání**.

- Vyberte **procesu** v **aktuální zobrazení** rozevíracího seznamu.

   Zobrazení procesů zobrazí tabulku, která zahrnuje **ID procesu**, **název procesu**, **začít čas**a **koncový čas**. Data lze seřadit klepnutím na názvy sloupců.

## <a name="see-also"></a>Viz také:

- [Návod: Používání hierarchie XSLT](../xml-tools/walkthrough-using-xslt-hierarchy.md)