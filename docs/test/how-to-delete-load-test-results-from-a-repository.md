---
title: "Postupy: odstranění výsledků zátěžového testu z úložiště v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- results, load test
- load tests, deleting results
- load test results, removing
- Load Test Results Repository
- load tests, removing results
- load test results, deleting
ms.assetid: c2afe36b-d061-4f0e-9580-c18569ec08f9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 0bdcc566b17d642ba4de2f476c2e8a96994da6f9
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-delete-load-test-results-from-a-repository"></a>Postupy: Odstranění výsledků zátěžového testu z úložiště

Při spuštění zátěžového testu informace, které byly získány při spuštění je uložen v úložišti testovací výsledky načíst. Úložiště výsledků zátěžových testů obsahuje data čítače výkonu a informace o všech chybách. Další informace najdete v tématu [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md).

 Výsledků zátěžového testu z editoru načíst testování můžete spravovat pomocí **otevřete a správa výsledků načíst testování** dialogové okno. Můžete otevřít, import, export a odebrat výsledků zátěžového testu.

## <a name="to-delete-results-from-a-repository"></a>Chcete-li odstranit výsledky z úložiště

1.  Z projektu testu výkonnosti webu a zátěžového testu otevřete zátěžový test.

2.  Na panelu nástrojů vložený zvolte **otevřete a správa výsledků**.

     **Otevřete a správa výsledků zátěžových testů** se zobrazí dialogové okno.

3.  V **zadejte název řadiče najít výsledků zátěžového testu**, vyberte řadič. Vyberte  **\<místní - žádný řadič >** přístup výsledky, které jsou uložené místně.

4.  V **zobrazit výsledky pro následující zátěžový test**, vyberte zátěžový test, jejichž výsledky, které chcete zobrazit. Vyberte  **\<zobrazit výsledky pro všechny testy >** zobrazíte všechny výsledky pro všechny testy.

     Pokud výsledků zátěžových testů jsou k dispozici, se objeví v **výsledků zátěžového testu** seznamu. Sloupce **čas**, **doba trvání**, **uživatele**, **výsledek**, **Test**, a  **Popis**. **Testování** obsahuje název testu a **popis** obsahuje nepovinný popis, který se přidá před spuštěním testu. **Popis** sloupec zobrazuje krátký popis, které byly zadány v **Analysis komentáře** pro tento test výsledek.

5.  V **výsledků zátěžového testu** vyberte výsledek. Chcete-li vybrat více než jeden výsledek můžete použít klávesu Shift a klávesu Ctrl.

6.  Zvolte **odebrat**.

     Výsledky se odeberou z úložiště.

    > [!NOTE]
    > **Otevřete a správa výsledků zátěžových testů** dialogové okno zůstane otevřený po odebrání výsledky.

## <a name="see-also"></a>Viz také

- [Postupy: Export výsledků zátěžového testu z úložiště](../test/how-to-export-load-test-results-from-a-repository.md)
- [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Import výsledků zátěžového testu do úložiště](../test/how-to-import-load-test-results-into-a-repository.md)