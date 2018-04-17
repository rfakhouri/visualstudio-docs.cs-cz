---
title: 'Postupy: Import výsledků zátěžového testu do úložiště v sadě Visual Studio | Microsoft Docs'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, importing
- Load Test Results Repository
- load tests, importing results
ms.assetid: a955b3d2-c8ad-40dd-8ea3-9f1a271e1eed
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 5a4646578299895c0988522d871ba727d80f063c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-import-load-test-results-into-a-repository"></a>Postupy: Import výsledků zátěžového testu do úložiště

Při spuštění zátěžového testu budou informace shromážděné za běhu uloženy v úložišti výsledků zátěžových testů. Úložiště výsledků zátěžových testů obsahuje data čítače výkonu a informace o všech chybách. Další informace najdete v tématu [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md).

 Výsledků zátěžového testu z editoru načíst testování můžete spravovat pomocí **otevřete a správa výsledků načíst testování** dialogové okno. Můžete otevřít, import, export a odebrat výsledků zátěžového testu.

## <a name="to-import-results-into-a-repository"></a>Chcete-li importovat výsledky do úložiště

1.  Z projektu testu výkonnosti webu a zátěžového testu otevřete zátěžový test.

2.  Na panelu nástrojů vložený zvolte **otevřete a správa výsledků**.

     **Otevřete a správa výsledků zátěžových testů** se zobrazí dialogové okno.

3.  V **zadejte název řadiče najít výsledků zátěžového testu**, vyberte řadič. Vyberte  **\<místní >** přístup výsledky ukládají místně.

     Pokud jsou k dispozici výsledků zátěžového testu, se objeví v **výsledků zátěžového testu** seznamu. Sloupce **čas**, **doba trvání**, **uživatele**, **výsledek**, **Test**, a  **Popis**. **Testování** obsahuje název testu a **popis** obsahuje nepovinný popis, který se přidá před spuštěním testu.

4.  Zvolte **Import**.

     **Import výsledků zátěžového testu** zobrazí se dialogové okno.

5.  V **název souboru** pole, zadejte název souboru výsledků archivovaný testu a pak zvolte **otevřete**.

     \- nebo –

     Přejděte na soubor a potom zvolte **otevřete**.

    > [!NOTE]
    > Soubor výsledků archivovaný test, který určíte v tomto kroku musí být vytvořen provedením operace exportu.

     Výsledky jsou importovány a zobrazují v **výsledků zátěžového testu** seznamu.

## <a name="see-also"></a>Viz také

- [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Export výsledků zátěžového testu z úložiště](../test/how-to-export-load-test-results-from-a-repository.md)