---
title: Testovacího Kontroléru a požadavky na Test Agent pro zátěžové testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, requirements
- controllers, requirements
ms.assetid: 372d97ce-12e4-46a9-9863-da508adba68f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6f2a598ba816b12ca7027495e3775d160a7aefd6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974855"
---
# <a name="test-controller-and-test-agent-requirements-for-load-testing"></a>Požadavky testovacího kontroléru a agenta Test Agent pro zátěžové testování

Některé testovací typy včetně jednotky, výkon webové, zatížení a manuálních testů jsou integrované do sady Visual Studio. Visual Studio umožňuje uživatelům Visual Studio – správa životního cyklu aplikací ke spuštění testů na vzdálených počítačích pomocí testovacího kontroléru a jednoho nebo více agentů. V tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="hardware-and-software-requirements"></a>Hardware a požadavky na Software

Testovací kontroler i počítače agenta test mít specifické požadavky na hardware a software. Kromě toho pokud chcete nasadit testovací kontroler a testovací počítače agenta napříč více jazyků, musíte naplánovat jak podporovat tyto jazyky.

### <a name="hardware-requirements"></a>Požadavky na hardware

V následující tabulce jsou uvedeny doporučené hardwarové požadavky pro nasazení testovacího kontroléru a testovacích agentů.

|**Konfigurace**|**Součást**|**CPU**|**HD**|**Paměť**|
|-----------------------|-------------------|-------------|------------|----------------|
|< 500 virtuálních uživatelů|Testovací agent|2.6 GHz|10 GB|2 GB|
|< 1 000 virtuálních uživatelů|Testovací agent|Dvoujádrový procesor 2.6 GHz|10 GB|2 GB|
|N x 1000 virtuálních uživatelů|Testovací agent|Horizontální navýšení kapacity N agentů pro každý s duální 2.6 Ghz|10GB|2GB|
|\< 30 počítačů v testovacím prostředí. To zahrnuje agenty a servery v rámci testu.|Testovací kontroler|2.6 GHz|||
|N x 30 počítačů v testovacím prostředí. To zahrnuje agenty a servery v rámci testu.|Testovací kontroler|N 2.6 GHz procesorů|||

> [!NOTE]
> Počet virtuálních uživatelů se bude lišit testu široce. Klíče příčinu této odchylky je odchylky *časy přemýšlení*, nebo zpoždění uživatele. Další informace najdete v tématu [úpravy dob uvažování pro simulaci webu lidského prodlev při interakci](../test/edit-think-times-in-load-test-scenarios.md). V zátěžový test testy webu jsou obecně efektivnější a generovat další zatížení než testování částí. Čísla v předchozí tabulce jsou platné pro spouštění webových testů pomocí časů přemýšlení 3 až 5 sekund na typické webové aplikace.

Pokyny, které jsou uvedeny v tomto tématu jsou uvedeny jako obecné pokyny pro plánování hardwaru. Testování výkonu se liší, výrazně podle množství dat, test a počet testovacích agentů. Pro testovací agenty rychlost procesoru a paměti, které jsou k dispozici omezí zkušební zatížení. Testovací kontrolery potřebovat větší prostředky, v závislosti na počtu testovacích agentů a objem dat zahrnutých do testů.

Server, který běží v sadě Visual Studio by měl mít spolehlivé síťové připojení s minimální šířku pásma 1 MB/s a latence maximálně 350ms. Měla by existovat žádné brány firewall mezi testovacích agentů a testovací kontroler. Pokud testování výkonu nesplňuje vaše očekávání, zvažte upgradování konfiguraci hardwaru.

### <a name="additional-hardware-considerations"></a>Další hardwarové požadavky

Testovací agenti generují velký objem dat na test řadičích, v závislosti na dobu trvání testu a velikost testu. Obecně platí měli byste naplánovat pro další 10 GB úložiště pevný disk pro každých 24 hodin testovacích datech.

Kromě hardwaru, doporučujeme tady měli byste zvážit další hardware pro kritické servery, například redundantní napájení a redundantní ventilátory.

### <a name="language-requirements"></a>Jazykové požadavky

Pokud chcete předejít nejasnostem a zjednodušují operace, měla by se nakonfigurovat testovací kontrolery a testovací agenty používat ve stejném jazyce jako operační systém a že produktu Team Foundation Server. Pokud na různých počítačích jsou nainstalovány agentem test agent a testovací kontroler, musejí být nakonfigurovány na použití stejné jazyka. Můžete však nainstalovat jinou jazykovou verzi sady Visual Studio v anglické verzi operačního systému, tak dlouho, dokud tento jazyk odpovídá nasazení Team Foundation Server.

## <a name="monitor-agent-resources"></a>Prostředky agenta monitorování

Můžete monitorovat počítače agenta k určení požadavků na prostředky pomocí sledování **QTAgent\*.exe** procesy, které spouštění a škálování během testů. Nejběžnějším problémovým místem na procesy QTAgent*.exe je využití procesoru. Pokud využití procesoru je konzistentně ve vysoké nineties je to znamenat, že výraznou načítá agenta. Další běžné problémovým místem je využití paměti. Pro náročné testy, monitorování těchto prostředků může pomoci zjistit, zda by měla zvýšit prostředky počítače nebo distribuce testů jinak.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)