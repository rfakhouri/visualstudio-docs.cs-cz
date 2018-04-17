---
title: Shromažďování diagnostických informací pomocí nastavení testů v sadě Visual Studio | Microsoft Docs
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 857425f1240536e0a0d9e7ebb1c00fed214d6535
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="collect-diagnostic-information-using-test-settings"></a>Shromažďování diagnostických informací s použitím nastavení testu

Můžete použít *nastavení testů* v sadě Visual Studio shromažďovat další data při spuštění testů. Například můžete chtít provést záznamu jako spustíte test videa. Existují adaptérů diagnostických dat na:

-   Shromažďovat každý krok akce uživatelského rozhraní v textovém formátu

-   Zaznamenávají každou akci uživatelského rozhraní pro přehrávání

-   Shromažďovat informace o systému

-   Shromažďování dat protokolu událostí

-   Shromáždění dat technologie IntelliTrace, který vám pomůže určit-reprodukovatelnou chyby

Adaptérů diagnostických dat lze také změnit chování testovací počítač. Například s nastavením testu v sadě Visual Studio, můžete emulovat různé topologie problémových míst v síti k vyhodnocení výkonu aplikace vašeho týmu.

## <a name="use-test-settings-with-visual-studio"></a>Pomocí nastavení testů pomocí sady Visual Studio

Pokud chcete spustit vaše jednotka, programové uživatelského rozhraní, výkon webové nebo zátěžových testů pomocí sady Visual Studio, můžete přidat, konfigurovat a vyberte nastavení testu pro použití při spouštění testů. Spouštění testů, shromažďování dat nebo ovlivnění testovacího počítače vzdáleně, je nutné zadat testovací kontroler pro použití v nastavení testu. Testovací kontroler bude mít agentů, které lze použít pro každou roli v nastavení testu.

## <a name="diagnostic-data-adapter-details"></a>Diagnostické informace adaptér dat

Následující tabulka obsahuje přehled o různých způsobech, adaptérů diagnostických dat může být nakonfigurována pro použití s rolí místního nebo vzdáleného počítače.

|Adaptér diagnostických dat, který se používá v nastavení testu|Manuální testy v místním počítači|Automatizované testy|Manuální testy: Shromažďování dat pomocí sadu role a prostředí|Poznámky|
|----------------------------------------------------------|-----------------------------------|---------------------|------------------------------------------------------------------------------|-----------|
|**Proxy server klienta ASP.NET pro IntelliTrace a dopadu testu:** tento proxy server umožňuje shromažďování informací o volání protokolu http od klienta na webový server pro adaptérů diagnostických dat IntelliTrace a dopadu testu.|Ano|Ano|Ano|-Používejte jenom v případě, že buď IntelliTrace nebo testovací dopad adaptérů diagnostických dat vybraných pro roli klienta.|
|**ASP.NET profiler:** můžete vytvořit testovací nastavení, které zahrnuje tvorbě profilace ASP.NET, který shromažďuje údaje o výkonu na webových aplikací ASP.NET.|Ne|Ano (viz poznámky)|Ne|-Tento adaptér diagnostických dat je podporována pouze v případě, že spouštění zátěžových testů ze sady Visual Studio.|
|**Pokrytí kódu:** vytvoříte nastavení testu, který obsahuje informace pokrytí kódu, který se používá k prozkoumání, kolik z kódu je předmětem testy.|Ne|Ano (viz poznámky)|Ne|-Pokrytí kódu můžete používat jenom v případě, že spuštění automatizovaných testů v sadě Visual Studio nebo mstest.exe a pouze z počítače spouští test. Vzdálené kolekce není podporována.<br />-Shromažďování dat o pokrytí kódu nebude fungovat, pokud máte také nastavení testu, který je nakonfigurován tak, aby shromažďování informací IntelliTrace. **Poznámka:** tento adaptér diagnostických dat platí pouze pro nastavení testů v sadě Visual Studio. Pro nastavení testů v nástroji Microsoft Test Manager se nepoužívá. Tento adaptér je navíc k zajištění kompatibility se test projektů Visual Studio 2010. **Poznámka:** pro kompatibilitu, pokrytí kódu platí při automatizované testy se spouštějí v nástroji Microsoft Test Manager nebo na vzdáleného agenta Test ze sady Visual Studio pomocí starší verze runner Mstestu.|
|**Protokol událostí:** můžete nakonfigurovat testu nastavení zahrnout shromažďování protokolu událostí, který bude součástí výsledků testů.|Ano|Ano|Ano||
|**IntelliTrace:** můžete nakonfigurovat adaptér diagnostických dat pro *IntelliTrace* lze shromažďovat informace o konkrétní diagnostické trasování lze izolovat chyby, které je obtížné reprodukovat. Tím se vytvoří soubor IntelliTrace, který obsahuje tyto informace. Soubor IntelliTrace s příponou .iTrace. Pokud se test nezdaří, můžete vytvořit chyby. Soubor IntelliTrace, který je uložen spolu s výsledky testů se automaticky propojení se této chyby. Data, která se shromažďují v souboru nástroje IntelliTrace zvyšuje produktivitu ladění snížením čas, který je potřeba reprodukujte a diagnostikovat chybu v kódu. Z této IntelliTrace soubor místní relace může být simulated na jiném počítači. Tím se snižuje riziko chyby probíhá jiný reprodukovatelnou.|Ano|Ano|Ano|– Pokud povolíte kolekce dat IntelliTrace, nebude fungovat kolekce dat pokrytí kódu.<br />– Pokud používáte IntelliTrace pro roli webového klienta, je nutné vybrat také proxy server ASP.NET klienta pro adaptér diagnostických dat IntelliTrace a dopadu testu.<br />-Jsou podporovány pouze následující verze služby IIS: Služba IIS 7.0, IIS 7.5 a IIS 8.0.|
|**Emulace sítě:** můžete určit, zda se mají umístit zatížení umělé sítě na svůj test s použitím nastavení testu. Emulace sítě s ovlivňuje komunikace do a z počítače pomocí emulace rychlost konkrétní síťového připojení, jako je například telefonického připojení. **Poznámka:**|Ne|Ano (viz poznámky)|Ne|Adaptér diagnostických dat emulace sítě můžete použít pro roli klienta nebo serveru. Není nutné používat adaptér na obě tyto role, které vzájemně komunikovat. **Poznámka:** tento adaptér diagnostických dat platí pouze pro nastavení testů v sadě Visual Studio. Pro nastavení testů v nástroji Microsoft Test Manager se nepoužívá. **Poznámka:** emulace sítě nelze použít ke zvýšení rychlosti připojení k síti. **Upozornění:** Pokud zahrnete síťový adaptér diagnostických dat emulace nastavení testů a máte v úmyslu použít na místním počítači, pak ovladač emulace sítě musí také vázat na jeden ze síťových adaptérů váš počítač. Ovladač emulace sítě je vyžadována pro adaptér diagnostických dat emulace sítě funkce. Ovladač emulace sítě je nainstalován a vázána na váš adaptér dvěma způsoby: <ul><li>**Ovladač emulace sítě s Microsoft Visual Studio Test Agent nainstalovat:** Microsoft Visual Studio Test Agent lze použít na vzdálených počítačích a v místním počítači. Když instalujete Visual Studio agentem Test Agent, proces instalace zahrnuje krok konfigurace, která se váže k síťové kartě ovladač emulace sítě. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).</li><li>**Ovladač emulace sítě s Microsoft Visual Studio Test Professional nainstalovat:** při použití emulace sítě poprvé, budete vyzváni k vytvoření vazby ovladač emulace sítě síťové karty.</li></ul> Můžete také nainstalovat ovladač emulace sítě z příkazového řádku na místním počítači bez instalace agenta pro testovací sady Visual Studio pomocí následujícího příkazu: **/VSTestConfig NETWORKEMULATION Install**  **Upozornění:** adaptér emulace sítě je ignorován v zátěžových testech. Zátěžové testy místo toho použijte nastavení, které jsou určené v síti směs scénáře zátěžového testu.|
|**Informace o systému:** nastavení testu můžete nastavit tak, aby zahrnují systémových informací o počítači, na kterém se test spustí.|Ano|Ano|Ano||
|**Testování dopad:** můžete shromáždit informace o tom, které byly používány metody kódu aplikace při spuštění testovacího případu. To lze použít společně s změny kódu aplikace, která byla vytvořená vývojáři k určení, které testy situace měla vliv na tyto změny vývoj.|Ano|Ano|Ano|– Pokud shromažďujete data dopadu testu pro roli webového klienta, je nutné vybrat také proxy server ASP.NET klienta pro adaptér diagnostických dat IntelliTrace a otestovat vliv.<br />-Jsou podporovány pouze následující verze služby IIS: Služba IIS 7.0, IIS 7.5 a IIS 8.0.|
|**Záznam videa:** můžete vytvořit záznam videa plochy relace při spuštění testu. Video může pomoci ostatní členové týmu izolovat aplikace problémy, které je obtížné reprodukovat.|Ano|Ano (viz poznámky)|Ano|– Pokud povolíte software agenta test ke spuštění jako proces místo služby, můžete vytvořit záznamu při spuštění automatizovaných testů videa.|