---
title: Vlastnosti scénáře zátěžového testu sady Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, scenarios
ms.assetid: 4414a638-1fa2-40ad-b1f4-b99f90b62e62
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 144a875822034ef3ae10a4f0cb5f1771ebf61fb7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="load-test-scenario-properties"></a>Vlastnosti scénáře zátěžového testu

Změňte nastavení zatížení testovací scénář vlastností v sadě Visual Studio pro splnění zatížení testování požadavky. V tomto článku jsou uvedené různé vlastnosti scénáře zátěžového testu podle kategorie.

## <a name="general"></a>Obecné

|Vlastnost|Definice|
|--------------|----------------|
|**Jméno**|Název scénáře|

## <a name="mix"></a>Kombinace

|Vlastnost|Definice|
|--------------|----------------|
|**Kombinace prohlížeče**|Určuje kombinaci webových prohlížečů pro zátěžový test. Lze určit různé typy webových prohlížečů a rozložení zátěže mezi nimi.<br /><br />Zvolte tlačítko se třemi tečkami (...) otevřete dialogové okno Upravit kombinace prohlížeče a používat **přidat** a **odebrat** a vyberte typy webových prohlížečů v zátěžovém testu.<br /><br />Další informace najdete v tématu [určení typů webových prohlížečů](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).|
|**Kombinace sítí**|Určuje kombinaci sítí pro zátěžový test. Můžete určit typy sítí, které chcete zahrnout, a rozložení zátěže mezi nimi.<br /><br />Zvolte tlačítko se třemi tečkami (...) otevřete **upravit kombinace sítí** dialogové okno a použijte **přidat** a **odebrat** a vyberte typy síťových v zátěžovém testu.<br /><br />Další informace najdete v tématu [určení typů virtuálních síťových](../test/specify-virtual-network-types-in-a-load-test-scenario.md).|
|**Poměr testů**|Určuje kombinaci testu výkonnosti webu a testu částí pro zátěžový test. Můžete určit, které testy budou zahrnuty, a rozložení zátěže mezi nimi.<br /><br />Zvolte tlačítko se třemi tečkami (...) otevřete **úpravy kombinace testů** dialogové okno a použijte **přidat** a **odebrat** vyberte testy v zátěžovém testu.<br /><br />Další informace najdete [úpravy kombinace testů pro scénáře zátěžového testu](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).|
|**Typ kombinace testů**|Určuje model kombinace testů pro zátěžový test.<br /><br />Zvolte tlačítko se třemi tečkami (...) otevřete **úpravy kombinace testů** dialogové okno a použijte rozevírací seznam v části **model kombinace testů** vyberte model kombinace testů pro použití v zátěžovém testu.<br /><br />Další informace najdete v tématu [úpravy modelů kombinací](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).|

## <a name="options"></a>Možnosti

|Vlastnost|Definice|
|--------------|----------------|
|**Agenti pro použití**|Určuje, že agentů, které chcete použít, pokud používáte zatížení váš scénář otestovat vzdáleně. Může být například potřeba určit konkrétní sadu agentů, aby byla při analýze trendů výkonu zachována konzistence. Agenty mohou být také geograficky rozmístěny tak, aby existovalo spřažení mezi spouštěnými skripty a umístěním agentu.<br /><br />Agenti musí být oddělené čárkami, například "**Agent1, Agent2, Agent3**". Je-li tato vlastnost ponechána prázdná, scénář bude používat všechny dostupné agenty.<br /><br />Další informace najdete v tématu [postupy: určení testovacích agentů pro použití](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md).|
|**Použití rozdělení pro zpoždění interval**|Logická hodnota, která slouží k určení, pokud chcete použít typické distribuce zpoždění při uživatele interval model kombinace testů. Tato vlastnost platí jenom v případě **typu kombinace testu** je nastavena na **na základě uživatele se stimulací podle**.<br /><br />Další informace najdete v tématu [postupy: použití distribuční interval zpoždění](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md)|
|**Přepínání IP**|Logická hodnota, která slouží k určení, pokud se používá přepínání IP.<br /><br />Přepínání IP umožňuje agentem test agent na odesílání žádostí na server pomocí řadu různých IP adres. To se simuluje volání, které pocházejí z různých klientských počítačů. Přepínání IP je důležité při testování s vyrovnáváním zatížení webové farmy. Většina nástrojů pro vyrovnávání zatížení vytvořit přidružení mezi klientem a konkrétní webový server pomocí IP adresy klienta. Pokud všechny požadavky působí, jako jsou pocházejících z jednoho klienta, nebudou nástroje pro vyrovnávání zatížení vyrovnávat zatížení. Chcete-li získat nástroj pro vyrovnávání zatížení dobrý ve webové farmě, je důležité, že požadavky pocházejí z rozsahu IP adres.<br /><br />Přepínání IP je k dispozici pouze u testovacího agentu.|
|**Maximálního počtu testovacích iterací**|Číselná hodnota, která určuje maximální počet testů, které budou spuštěny ve scénáři. Hodnota 0 neurčuje žádné maximum.<br /><br />Další informace najdete v tématu [konfigurace iterací testů ve scénářích](../test/configure-test-iterations-in-a-load-test-scenario.md).|
|**Procento nových uživatelů**|Číselná hodnota určující procentuální podíl nových uživatelů nebo prvních návštěvníků ve scénáři.<br /><br />Další informace najdete v tématu [postup: Zadejte procento virtuálních uživatelů dat pomocí webové mezipaměti](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md).|
|**Vezměte v úvahu profilu**|Určuje, pokud budou používat tento scénář **normálního rozdělení**, nebo pokud je profil uvažování **na** nebo **vypnout**.<br /><br />Další informace najdete v tématu [úpravy dob uvažování pro simulaci webu lidského prodlev při interakci](../test/edit-think-times-in-load-test-scenarios.md).|

## <a name="timing"></a>Časování

|Vlastnost|Definice|
|--------------|----------------|
|**Čas zahájení zpoždění**|Časová hodnota, která označuje, kolik hodin, minut a sekund bude trvat zpoždění spuštění po spuštění zátěžového testu. Pokud **zakázat během zahřívání** je nastavena na **True**, dobu čekání platí po dokončení warm-up období.<br /><br />Další informace najdete v tématu [zpoždění spuštění scénáře konfigurace](../test/configure-scenario-start-delays.md).|
|**Zakázat dobu zahřívání**|Logická hodnota, která slouží k určení, pokud se tento scénář se má spustit nebo není během **záložním trvání** hodnota vlastnosti doba zadaná v zátěžovém testu je spustit nastavení.<br /><br />Další informace o zátěžový test, spusťte vlastnosti nastavení najdete v tématu [načíst testovací nastavení vlastnosti spustit](../test/load-test-run-settings-properties.md).<br /><br />Další informace najdete v tématu [zpoždění spuštění scénáře konfigurace](../test/configure-scenario-start-delays.md).|
|**Vezměte v úvahu dobu mezi testovacími iteracemi**|Číselná hodnota, která se používá k určení doby čekání v sekundách mezi iteracemi testu.<br /><br />Další informace najdete v tématu [úpravy dob uvažování pro simulaci webu lidského prodlev při interakci](../test/edit-think-times-in-load-test-scenarios.md).|

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)