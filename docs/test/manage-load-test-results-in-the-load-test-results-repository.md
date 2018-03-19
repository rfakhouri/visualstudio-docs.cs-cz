---
title: "Správa výsledků zátěžových testů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
ms.assetid: 1cd63c4b-4f74-4133-b675-5e8fbeab25f3
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: f5b09a2350efadafaacdc5fcd530b3c3f50c7419
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="manage-load-test-results-in-the-load-test-results-repository"></a>Správa výsledků zátěžových testů v úložiště výsledků zátěžového testu

Když spustíte zátěžových testů, všechny informace shromážděné během spuštění zátěžového testu můžou být uložené v *zatížení úložiště výsledků testů*, což je databáze SQL. Úložiště výsledků zátěžového testu obsahuje data čítače výkonu a žádné informace o zaznamenané chyby. Úložiště výsledků databáze je vytvořený programem setup pro řadiče nebo vytvoří automaticky v první místní spuštění zátěžového testu. Pro spuštění místní databázi vytvoří se automaticky pokud neexistuje schéma testu zatížení.

 Pokud upravíte kontroleru výsledky úložiště připojovací řetězec k použití na jiný server, na nový server musí mít loadtestresultsrepository.sql skript pro vytvoření schématu spustit.

 Visual Studio Enterprise poskytuje sady s názvem čítačů, které shromažďovat běžné čítače výkonu, které jsou založené na technologie. Tyto sady jsou užitečné při analýze serveru se službou IIS, serveru ASP.NET nebo SQL server. Veškerá data shromážděná pomocí sad čítačů je uložená v úložiště výsledků zátěžového testu.

> [!IMPORTANT]
> Existuje rozdíl mezi sady čítačů a data čítače výkonu. Sady čítačů jsou metadata. Definuje skupinu čítače výkonu, které by měly být shromažďovány z počítače, který provádí konkrétní roli jako služby IIS nebo SQL Server. Čítač sada je součástí definice testu zatížení. Se shromažďují data čítače výkonu na základě na sady čítačů, mapování čítač nastavit na určitý počítač a vzorkovací frekvence.

## <a name="sql-server-versions"></a>Verze systému SQL Server

 Pokud chcete používat zátěžových testů, můžete použít SQL Server Express LocalDB, který je nainstalován pomocí sady Visual Studio. Je výchozí databázový server pro zátěžové testy (včetně integrace aplikace Microsoft Excel). SQL Server Express LocalDB je provádění režim systému SQL Server Express, který je zaměřený na vývojáře program. Instalace SQL serveru Express LocalDB zkopíruje minimální sadu souborů, které jsou nutné ke spuštění databázového stroje SQL Server.

 Pokud váš tým očekává potřeby velkou databáze nebo projekty odrůst SQL Server Express LocalDB, měli byste zvážit, upgrade na buď SQL Express nebo úplným SQL serverem zajistit další škálování potenciální. Pokud provádíte upgrade systému SQL Server, soubory MDF a LDF pro SQL Server Express LocalDB jsou uloženy ve složce profilu uživatele. Tyto soubory můžete použít k importování databáze testu zatížení do systému SQL Server Express nebo SQL Server.

## <a name="load-test-results-store-considerations"></a>Důležité informace o ukládání výsledků zátěžového testu

 Pokud Visual Studio Enterprise je nainstalovaná, uložení výsledků zátěžového testu nastavit použití instance systému SQL Express, který je nainstalován v počítači. SQL Express je omezeno na použití maximálně 4 GB místa na disku. Chcete-li spustit mnoho zátěžových testů po dlouhou dobu, měli byste zvážit, konfigurace, které úložiště výsledků zátěžového testu použití instance úplné produktu SQL Server, pokud je k dispozici.

## <a name="load-test-analyzer-tasks"></a>Spouštění testovací úlohy analyzátoru

|Úlohy|Související témata|
|-----------|-----------------------|
|**Úložiště výsledků zátěžového testu nastavení:** můžete nastavit úložiště výsledků zátěžového testu v databázi SQL. **Poznámka:** úložiště zátěžového testu můžete taky vytvoří při instalaci testovací kontroler. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).||
|**Výběr a zobrazení výsledků úložiště:** můžete vybrat konkrétní výsledky úložiště. Nejste omezený na místní výsledky úložiště. Často zátěžové testy se spouštějí na sadu vzdáleného počítače agenta. Výsledky testů z agenty nebo místního počítače můžete uložit do všech ostatních SQL serverech, na který jste vytvořili uložení výsledků zátěžového testu. V obou případech je potřeba určit, kam se mají ukládat vaše výsledků zátěžového testu pomocí **spravovat testování řadiče** okno.|-   [Postupy: Výběr úložiště výsledků zátěžového testu](../test/how-to-select-a-load-test-results-repository.md)<br />-   [Postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)|
|**Odstranění výsledků testů zatížení z úložiště:** můžete odebrat výsledek testu zatížení z **načíst Editor testů** pomocí **otevřete a správa výsledků načíst testování** dialogové okno.|-   [Postupy: odstranění výsledků zátěžového testu z úložiště](../test/how-to-delete-load-test-results-from-a-repository.md)|
|**Importovat a exportovat výsledky do úložiště:** můžete importovat a exportovat výsledků zátěžového testu z **načíst Editor testů**.|-   [Postupy: Import výsledků zátěžového testu do úložiště](../test/how-to-import-load-test-results-into-a-repository.md)<br />-   [Postupy: Export výsledků zátěžového testu z úložiště](../test/how-to-export-load-test-results-from-a-repository.md)|

## <a name="related-tasks"></a>Související úlohy

 [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

 Výsledky testu běžící zatížení a dokončeného zátěžového testu můžete zobrazit pomocí analyzátoru načíst testování.

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)