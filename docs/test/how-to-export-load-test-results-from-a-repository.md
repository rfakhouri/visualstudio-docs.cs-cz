---
title: Export výsledků zátěžového testu
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load tests, exporting results
- Load Test Results Repository
- load test results, exporting
ms.assetid: 716c2af5-8737-4d31-956f-a0273f7c5c0c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7bc496c4f6a445ffd43e992302457bdb92f3239a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949860"
---
# <a name="how-to-export-load-test-results-from-a-repository"></a>Postupy: Export výsledků zátěžového testu z úložiště

Při spuštění zátěžového testu budou informace shromážděné za běhu uloženy v úložišti výsledků zátěžových testů. Úložiště výsledků zátěžových testů obsahuje data čítače výkonu a informace o všech chybách. Další informace najdete v tématu [výsledků zátěžového testu spravovat v úložiště výsledků testu zátěže](../test/manage-load-test-results-in-the-load-test-results-repository.md).

Výsledky zátěžového testu můžete spravovat z editoru zátěžového testu pomocí **otevřít a spravovat výsledky zátěžového testu** dialogové okno. Můžete otevřít, importovat, exportovat a odstranit výsledky zátěžových testů.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-export-results-from-a-repository"></a>Export výsledků z úložiště

1.  Z webového výkonu a zátěžové testování projektu, otevřete zátěžový test.

2.  Na panelu nástrojů themeroller vložený **otevřít a spravovat výsledky**.

     **Otevřít a spravovat výsledky zátěžového testu** se zobrazí dialogové okno.

3.  V **zadat název kontroléru pro vyhledání výsledků zátěžového testu**, vyberte řadič. Vyberte  **\<místní – žádný kontrolér >** pro přístup k výsledkům uloženým místně.

4.  V **zobrazit výsledky pro následující zátěžový test**, vyberte test zatížení, jejichž výsledky chcete zobrazit. Vyberte  **\<zobrazit výsledky všech testů >** zobrazíte všechny výsledky pro všechny testy.

     Pokud výsledky zátěžového testu jsou k dispozici, jsou uvedeny v **výsledky zátěžového testu** seznamu. Sloupce jsou **čas**, **doba trvání**, **uživatele**, **výsledek**, **testovací**, a  **Popis**. **Testování** obsahuje název testu, a **popis** obsahuje volitelný popis, který je přidán před spuštěním testu. **Popis** sloupec zobrazuje krátké popisy, které byly zadány v **komentáře analýzy** pro tento výsledek testu.

5.  V **výsledky zátěžového testu** seznamu, vyberte výsledek. Můžete použít **Shift** klíč, **Ctrl** klíč, nebo obojí, vyberte více než jeden výsledek a exportovat je do jednoho souboru.

6.  Zvolte **exportovat**.

     **Exportovat výsledky zátěžového testu** zobrazí se dialogové okno.

7.  V **název_souboru** pole, zadejte název a klikněte na tlačítko **Uložit**.

     Výsledky budou exportovány do souboru archivu.

    > [!NOTE]
    > **Otevřít a spravovat výsledky zátěžového testu** dialogové okno zůstane otevřený po zobrazení výsledků.

## <a name="see-also"></a>Viz také:

- [Správa výsledků zátěžových testů v úložiště výsledků testu zátěže](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Postupy: Odstranění z úložiště výsledků zátěžového testu](../test/how-to-delete-load-test-results-from-a-repository.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Importovat do úložiště výsledků zátěžového testu](../test/how-to-import-load-test-results-into-a-repository.md)