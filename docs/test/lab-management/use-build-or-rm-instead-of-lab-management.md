---
title: Použití sestavení nebo Release Management pro automatizované testování v sadě Visual Studio
ms.date: 03/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- automated testing, lab management, test lab
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 454407c3572f7a7c7a1c0f795462d2aec539049a
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845376"
---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>Použití sestavení a správu verzí místo Lab Management pro automatizované testování

Pokud používáte Microsoft Test Manager (MTM) a Lab Management pro automatizované testování nebo pro automatizaci sestavení nasazení testování, toto téma vysvětluje, jak můžete dosáhnout pomocí stejné cíle [sestavení a verze](/vsts/build-release/) funkce v prostředí Team Foundation Server (TFS) a Visual Studio Team Services (služby VSTS).

## <a name="build-deploy-test-automation"></a>Automatizace sestavení nasazení testování

MTM a Lab Management závisí na definici sestavení jazyka XAML pro automatizaci sestavení, nasazení a testování aplikací. Sestavení XAML spoléhá na různé konstrukce vytvořené v MTM například testovacím prostředí, testovacích sad a testovacích nastavení a na různých komponent infrastruktury, například řadič sestavení, agenty sestavení, testovacího kontroléru a testovacích agentů k tomuto účelu. Můžete provést stejný pomocí méně kroků pomocí sestavení nebo správy verzí v sadě TFS a Team Services.

| Kroky | S sestavení jazyka XAML | Sestavení nebo Správa verzí |
|-------|----------------------|-----------------|
| Identifikujte počítače k nasazení na sestavení a spuštění testů. | Vytvořte standardní testovací prostředí v MTM s tyto počítače. | není k dispozici |
| Identifikujte testů ke spuštění. | Vytvoření sady testů v MTM, vytvoření testovacích případů a automatizace přidružit každý testovacího případu. Vytvoření nastavení testu v MTM identifikace roli počítačů v testovacím prostředí, ve kterém by měl být spuštěn testy. | Vytvořte automatizované testovací sady v MTM stejným způsobem, pokud máte v úmyslu spravovat testování pomocí testovacích plánů. To můžete přeskočit případně, pokud chcete spustit testy přímo z binárních souborů testovací vyprodukované buildy. Není nutné k vytváření nastavení testů v obou případech. |
| Automatizovat nasazení a testování. | Vytvořte definici sestavení jazyka XAML pomocí LabDefaultTemplate.*.xaml. Zadejte sestavení, sad testů a testovací prostředí v definici sestavení. | Vytvoření [sestavení nebo verze definice](/vsts/build-release/) s jedno prostředí. Spusťte stejné nasazovací skript (z definice sestavení XAML) pomocí úlohy příkazového řádku a spuštění automatizovaných testů pomocí úloh pro nasazení testovacího agenta a spuštění funkčních testů. Zadejte seznam počítačů a jejich přihlašovacích údajů jako vstupy pro tyto úlohy. |

Mezi výhody používání sestavení nebo Release Management pro tento scénář patří:

* Nepotřebujete řadič sestavení nebo testovací kontroler.
* Testovací agent byl nainstalován prostřednictvím úlohu jako součást sestavení nebo verzi.
* Je snadno přizpůsobit kroky nasazení. Již nejsou omezeny na pomocí jednoho skriptu. Můžete také využít mnoho úloh, které jsou k dispozici v rámci produktu také jako Visual Studio Marketplace.
* Nemáte udržovat testovacích sad. Testy můžete spustit přímo z binárních souborů.
* Získáte bohatší vložené reporting prostředí pro testy, které byly spuštěny v rámci každé sestavení nebo verzi.
* Můžete sledovat, které prostředky (verze, sestavení, pracovních položek, potvrzení) jsou aktuálně nasadila a otestovala na každé prostředí.
* Můžete přizpůsobit a rozšířit automatizace na snadno nasadit pro testovací prostředí s více a to i do produkčního prostředí.
* Můžete naplánovat automatizace provést vždy, když dojde k vrácení se změnami nebo potvrzení, nebo v určitý čas každý den.

## <a name="self-service-management-of-scvmm-environments"></a>Samoobslužné služby správu prostředí SCVMM

[Testovací Center v nástroji Microsoft Test Manager](/vsts/manual-test/mtm/guidance-mtm-usage) podporuje možnost spravovat knihovny šablon prostředí a také zřízení prostředí na vyžádání pomocí [SCVMM server](/system-center/vmm/overview?view=sc-vmm-1801).

Samoobslužné zřizování funkce testovacího prostředí centra mít dva odlišné cíle:

* Zadejte jednodušší způsob, jak spravovat infrastrukturu. Mezi příklady infrastruktury správy byly správu šablon virtuálních počítačů a prostředí a automaticky vytvoří soukromých sítích klony prostředí od sebe navzájem izolovat.

* Poskytují jednodušší způsob, jak týmy využívat virtuální počítače v jejich aktivity testování a nasazení. Vytvoření testovacího prostředí, které prostředí přístupné prostřednictvím stejného modelu zabezpečení týmového projektu a integrované použít z těchto virtuálních počítačů v testovací scénáře byly příklady snadné požívání.

Však zadána vývoj bohatší veřejného a soukromého cloudu systémy správy, jako [Microsoft Azure](https://azure.microsoft.com/) a [Microsoft Azure zásobníku](https://azure.microsoft.com/overview/azure-stack/), neexistuje žádný vývoj funkcím pro správu infrastruktury 2017 sady TFS a dále. Místo toho bude pokračovat zaměřuje na snadno spotřebu prostředků, které jsou spravované prostřednictvím těchto cloudových infrastruktur.

Následující tabulka shrnuje typické aktivit, které můžete provádět v testovacím Center a způsob provádění je pomocí SCVMM nebo Azure (Pokud se jedná o aktivitách řízení infrastruktury) nebo prostřednictvím sady TFS a Team Services (pokud jsou aktivity testu nebo nasazení):

| Kroky | S centrem testovacího prostředí | Sestavení nebo Správa verzí |
|-------|----------------------|-----------------|
| Spravujte knihovny šablon prostředí. | Vytvořte testovací prostředí. Na virtuálních počítačích nainstalujte potřebný software. Nástroj Sysprep a úložiště v prostředí jako šablona v knihovně. | Pomocí konzoly pro správu SCVMM přímo k vytváření a správě šablon virtuálních počítačů nebo šablony služby. Pokud používáte Azure, vyberte jednu z [šablony Azure rychlý Start](https://azure.microsoft.com/resources/templates/). |
| Vytvořte testovací prostředí. | Vyberte šablonu prostředí v knihovně a nasaďte ji. Zadejte potřebné parametry k přizpůsobení konfigurace virtuálních počítačů. | Pomocí konzoly pro správu SCVMM přímo k vytvoření virtuálních počítačů nebo instancí služby ze šablony. Přímo do vytváření prostředků pomocí portálu Azure. Nebo vytvářet verze definice v prostředí. Použití Azure úlohy nebo úlohy z [SCVMM integrace rozšíření](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) k vytvoření nových virtuálních počítačů. Vytvoření nové verze této definice je ekvivalentní k vytvoření nového prostředí v testovacím centru. |
| Připojte k počítačům. | Otevřete v prohlížeči prostředí testovacího prostředí. | Pomocí konzoly pro správu SCVMM přímo se připojit k virtuálním počítačům. Alternativně použijte IP adresy nebo názvy DNS virtuálních počítačů k otevření relace vzdálené plochy. |
| Pořízení kontrolního bodu prostředí nebo obnovit prostředí do čistého kontrolní bod. | Otevřete v prohlížeči prostředí testovacího prostředí. Vyberte možnost k pořízení kontrolního bodu nebo k obnovení do předchozího kontrolního bodu. | Pomocí konzoly pro správu SCVMM přímo k provádění těchto operací na virtuálních počítačích. Nebo, proveďte tyto kroky jako součást větší automatizace, zahrňte kontrolního bodu úlohy z [SCVMM integrace rozšíření](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) v rámci prostředí v definici verze. |

## <a name="creation-of-network-isolated-environments"></a>Vytvoření prostředí izolované sítě

Izolované testovací prostředí sítě je skupina SCVMM virtuálních počítačů, které se dají bezpečně klonovat aniž by to způsobilo sítě je v konfliktu. K tomu bylo potřeba v MTM pomocí řady pokyny, které slouží ke konfiguraci virtuálních počítačů ve veřejné síti sada síťových karet ke konfiguraci virtuálních počítačů v privátní síti a další sadu síťových karet.

Ale služby VSTS TFS ve spojení se SCVMM sestavení a úloha nasazení, můžete použít ke správě prostředí SCVMM zřídit izolované virtuální sítě a implementovat scénáře sestavení nasazení testování. Například můžete provádět úlohy:

* Vytvoření, obnovení a odstraňte kontrolní body
* Vytvoření nových virtuálních počítačů pomocí šablony
* Spuštění a zastavení virtuálních počítačů
* Spustit vlastní skripty prostředí PowerShell pro SCVMM

Další informace najdete v tématu [vytvořit virtuální izolovaného síťového prostředí pro sestavení nasazení testování scénáře](/vsts/build-release/actions/virtual-networks/create-virtual-network).
