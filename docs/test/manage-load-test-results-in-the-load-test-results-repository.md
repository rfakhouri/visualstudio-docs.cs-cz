---
title: Spravovat výsledky zátěžového testu
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, results repository
- results, load test
- load test results, repository
- Load Test Results Repository
ms.assetid: 1cd63c4b-4f74-4133-b675-5e8fbeab25f3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.openlocfilehash: 311d043d493d6958afae8a4217b42ba5abcd05f8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952363"
---
# <a name="manage-load-test-results-in-the-load-test-results-repository"></a>Správa výsledků zátěžových testů v úložiště výsledků testu zátěže

Při spuštění zátěžových testů v mohou být uloženy všechny informace shromážděné během spuštění zátěžového testu *úložiště výsledků testu zátěže*, což je databáze SQL. Úložiště výsledků zátěžového testu obsahují data čítače výkonu a veškeré informace o zaznamenaných chybách. Databáze úložiště výsledků je vytvořena instalačním programem řadiče, nebo vytvořena automaticky při prvním místním spuštění zátěžového testu. Pro místní spuštění databáze se vytvoří automaticky pokud neexistuje schéma zátěžového testu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Pokud změníte připojovací řetězec úložiště kontroleru výsledků použít jiný server, musí mít nový server *loadtestresultsrepository.sql* spustit skript k vytvoření schématu.

Visual Studio Enterprise obsahuje čítače pojmenované sady, které shromažďují společné čítače výkonu, které jsou založeny na technologii. Tyto sady jsou užitečné při analýze serveru IIS, serveru ASP.NET nebo SQL server. Všechna data shromážděná pomocí sady čítačů je uložen v úložišti výsledků zátěžového testu.

> [!IMPORTANT]
> Existuje rozdíl mezi sadou čítačů a daty čítačů výkonu. Sada čítačů jsou metadata. Definuje skupinu čítačů výkonu, které by měly být shromažďovány z počítače, který provádí určité role, jako je například IIS nebo SQL Server. Sada čítačů je součástí definice zkušebního zatížení. Data čítače výkonu jsou shromažďovány na základě na sady čítačů, mapování čítače nastaveny na určitý počítač a vzorkovací frekvenci.

## <a name="sql-server-versions"></a>Verze systému SQL Server

 Chcete-li použít testy zatížení, můžete použít SQL Server Express LocalDB, který je nainstalován se sadou Visual Studio. Je výchozím databázovým serverem pro zátěžové testy (včetně integrace aplikace Microsoft Excel). SQL Server Express LocalDB je režimem spuštění SQL serveru Express, která je určená pro vývojáře programu. Instalace SQL serveru Express LocalDB zkopíruje minimum souborů nutných ke spuštění databázového stroje SQL Server.

 Pokud váš tým očekává potřeby velkých databází nebo velký růst projektů SQL Server Express LocalDB, měli byste zvážit upgrade na SQL Express nebo úplný SQL Server k získání dalších možností škálování. Pokud upgradujete SQL Server, soubory MDF a LDF pro SQL Server Express LocalDB jsou uloženy ve složce profilu uživatele. Tyto soubory lze použít k importu databáze zátěžového testu na SQL Server Express nebo SQL Server.

## <a name="load-test-results-store-considerations"></a>Zvážení úložiště výsledků zátěžového testu

 Při instalaci sady Visual Studio Enterprise, úložiště výsledků zátěžového testu je nastavený na použití instance SQL Express, který je nainstalován v počítači. Systém SQL Express je omezen na maximálně 4 GB místa na disku. Pokud spustíte mnoho zátěžových testů po dlouhou dobu, měli byste zvážit konfiguraci úložiště výsledků zátěžového testu, aby používalo instanci plné verze produktu SQL Server, pokud je k dispozici.

## <a name="load-test-analyzer-tasks"></a>Načtení úlohy Analyzéru testu

|Úlohy|Související témata|
|-|-----------------------|
|**Nastavte úložiště výsledků zátěžového testu:** Můžete nastavit úložiště výsledků zátěžového testu na SQL database. **Poznámka:**  Úložiště zátěžového testu můžete také vytvořit při instalaci řadiče testu. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).||
|**Výběr a zobrazení úložiště výsledků:** Můžete vybrat konkrétní úložiště výsledků. Nejste omezeni na úložiště místních výsledků. Často jsou zátěžové testy spuštěny na vzdálené sadě počítačů agentů. Výsledky testu z agentů nebo místního počítače můžete uložit na každý serversql, na kterém jste vytvořili úložiště výsledků zátěžového testu. V obou případech je nutné určit, kam se mají ukládat výsledky zátěžového testu s použitím **Správa testovacích Kontrolérů** okna.|-   [Jak: Vyberte úložiště výsledků zátěžového testu](../test/how-to-select-a-load-test-results-repository.md)<br />-   [Jak: Přístup k analýze výsledků zátěžového testu](../test/how-to-access-load-test-results-for-analysis.md)|
|**Odstranění výsledku zátěžového testu z úložiště:** Můžete odebrat výsledek zátěžového testu z **editoru zátěžového testu** pomocí **otevřít a spravovat výsledky zátěžového testu** dialogové okno.|-   [Jak: Odstranění z úložiště výsledků zátěžového testu](../test/how-to-delete-load-test-results-from-a-repository.md)|
|**Importovat a exportovat výsledky do úložiště:** Můžete importovat a exportovat výsledky zátěžových testů z **editoru zátěžového testu**.|-   [Jak: Importovat do úložiště výsledků zátěžového testu](../test/how-to-import-load-test-results-into-a-repository.md)<br />-   [Jak: Export výsledků zátěžového testu z úložiště](../test/how-to-export-load-test-results-from-a-repository.md)|

## <a name="related-tasks"></a>Související úlohy

 [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

 Výsledky probíhajícího zátěžového testu i dokončeného zátěžového testu můžete zobrazit pomocí **Analyzéru zátěžového testu**.

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Postupy: Přístup k analýze výsledků zátěžového testu](../test/how-to-access-load-test-results-for-analysis.md)