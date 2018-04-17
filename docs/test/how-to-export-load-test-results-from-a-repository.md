---
title: Export výsledků zátěžových testů v sadě Visual Studio | Microsoft Docs
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
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: ce17cba842faf56205d5769bbcccfcdce8db6fec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-export-load-test-results-from-a-repository"></a>Postupy: Export výsledků zátěžového testu z úložiště

Při spuštění zátěžového testu budou informace shromážděné za běhu uloženy v úložišti výsledků zátěžových testů. Úložiště výsledků zátěžových testů obsahuje data čítače výkonu a informace o všech chybách. Další informace najdete v tématu [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md).

Výsledků zátěžového testu z editoru načíst testování můžete spravovat pomocí **otevřete a správa výsledků načíst testování** dialogové okno. Můžete otevřít, import, export a odebrat výsledků zátěžového testu.

## <a name="to-export-results-from-a-repository"></a>Export výsledků z úložiště

1.  Z projektu testu výkonnosti webu a zátěžového testu otevřete zátěžový test.

2.  Na panelu nástrojů vložený zvolte **otevřete a správa výsledků**.

     **Otevřete a správa výsledků zátěžových testů** se zobrazí dialogové okno.

3.  V **zadejte název řadiče najít výsledků zátěžového testu**, vyberte řadič. Vyberte  **\<místní - žádný řadič >** přístup výsledky ukládají místně.

4.  V **zobrazit výsledky pro následující zátěžový test**, vyberte zátěžový test, jejichž výsledky, které chcete zobrazit. Vyberte  **\<zobrazit výsledky pro všechny testy >** zobrazíte všechny výsledky pro všechny testy.

     Pokud výsledků zátěžových testů jsou k dispozici, se objeví v **výsledků zátěžového testu** seznamu. Sloupce **čas**, **doba trvání**, **uživatele**, **výsledek**, **Test**, a  **Popis**. **Testování** obsahuje název testu a **popis** obsahuje nepovinný popis, který se přidá před spuštěním testu. **Popis** sloupec zobrazuje krátký popis, které byly zadány v **Analysis komentáře** pro tento test výsledek.

5.  V **výsledků zátěžového testu** vyberte výsledek. Chcete-li vybrat více výsledků a exportovat je do jednoho souboru, použijte klávesu Shift, Ctrl nebo obě.

6.  Zvolte **exportovat**.

     **Export výsledků zátěžového testu** zobrazí se dialogové okno.

7.  V **název souboru** pole, zadejte název a potom zvolte **Uložit**.

     Výsledky budou exportovány do souboru archivu.

    > [!NOTE]
    > **Otevřete a správa výsledků zátěžových testů** dialogové okno zůstane otevřený po výsledky se zobrazí.

## <a name="see-also"></a>Viz také

- [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Postupy: odstranění výsledků zátěžového testu z úložiště](../test/how-to-delete-load-test-results-from-a-repository.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Import výsledků zátěžového testu do úložiště](../test/how-to-import-load-test-results-into-a-repository.md)