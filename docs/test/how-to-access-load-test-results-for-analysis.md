---
title: Analýza výsledků zátěžových testů v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, accessing
- Load Test Viewer
- load tests, accessing
- load tests, analyzing
- load tests, results
- Load Test Viewer, viewing
ms.assetid: b0a3e694-2894-479b-b270-7e61e9fafacd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: d20754bc61a003b1b7f6d1eb84ce419c2c6e442b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31966684"
---
# <a name="how-to-access-load-test-results-for-analysis"></a>Postupy: Přístup k výsledkům zátěžového testu pro analýzu

Při spuštění zátěžového testu z editoru načíst otestovat, automaticky otevře výsledků zátěžových testů a spuštěné zátěžového testu se zobrazí v analyzátoru načíst testování. Při spuštění zátěžového testu z příkazového řádku, je nutné ručně získat přístup výsledků zátěžového testu.

Výsledek testu zatížení pro dokončeného zátěžového testu obsahuje vzorků a informace o chybě, která nebyla shromážděna pravidelně z počítačů v rámci testu. Během spuštění zátěžového testu se můžou shromažďovat velký počet vzorků. Množství dat výkonu, která se shromažďují závisí na délce testu, spuštění, intervalu vzorkování, počet počítačů v rámci testů, počet shromažďovaných čítače, sběrače dat, které jsou nakonfigurované a úrovně protokolování. Pro velké zátěžový test množství dat výkonu, která se shromažďují lze snadno několik GB. Další informace najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

## <a name="to-access-a-load-test-result"></a>Pro přístup k výsledku testu zatížení

1.  Z projektu testu výkonnosti webu a zátěžového testu otevřete zátěžový test.

2.  V panelu nástrojů editoru zátěžových testů, vyberte **otevřete a správa výsledků** tlačítko.

     **Otevřete a správa výsledků** zobrazí se dialogové okno.

3.  V **zadejte název řadiče najít výsledků zátěžového testu**, vyberte řadič. Vyberte  **\<místní >-žádný řadič** přístup výsledky ukládají místně.

4.  V **zobrazit výsledky pro následující zátěžový test**, vyberte zátěžový test, jejichž výsledky, které chcete zobrazit. Vyberte  **\<zobrazit výsledky pro všechny testy >** zobrazíte všechny výsledky pro všechny testy.

     Pokud jsou k dispozici výsledků zátěžového testu, se objeví v **výsledků zátěžového testu** seznamu. Sloupce **čas**, **doba trvání**, **uživatele**, **výsledek**, **Test**, a  **Popis**. **Testování** obsahuje název testu a **popis** obsahuje nepovinný popis, který se přidá před spuštěním testu.

    > [!NOTE]
    > Výsledky se zobrazí ve výsledcích nejnovější v horní části seznamu.

5.  V **výsledků zátěžového testu** vyberte výsledků zátěžových testů, které chcete analyzovat a zvolte **otevřete**.

6.  Zobrazí se Analyzéru zátěžového testu. Výsledek testu vybrané zatížení se zobrazí v souhrnné zobrazení. Další informace najdete v tématu [přehled souhrnu výsledků testu zatížení](../test/load-test-results-summary-overview.md).

     Další aspekty výsledků zátěžových testů v otevřete dialogové okno a správa výsledků včetně import, export a odebrání výsledků zátěžových testů můžete spravovat. Další informace najdete v tématu [Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu](../test/manage-load-test-results-in-the-load-test-results-repository.md).

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)