---
title: "Použití sestavení nebo Release Management pro automatizované testování | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: automated testing, lab management, test lab
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 4dae17012ecf66258d65ff3c200a0dbe8e4c9429
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>Použití sestavení a správu verzí místo Lab Management pro automatizované testování

Pokud používáte Microsoft Test Manager (MTM) a Lab Management pro automatizované testování nebo pro automatizaci sestavení nasazení testování, toto téma vysvětluje, jak můžete dosáhnout pomocí stejné cíle [sestavení &amp; verze](https://www.visualstudio.com/team-services/continuous-integration/) funkce v týmu Foundation Server (TFS) a Visual Studio Team Services:

* [Automatizace sestavení nasazení testování](#bdtautomation)

* [Samoobslužné služby správu prostředí SCVMM](#managescvmm)

Sestavení a správu verzí nepodporují samoobslužné vytvoření prostředí SCVMM izolované sítě, a neexistují žádné plány, které podporují tento v budoucnu. Existují však některé [navrhované alternativy](#isolatedenvir).

<a name="bdtautomation"></a>
## <a name="build-deploy-test-automation"></a>Automatizace sestavení nasazení testování

MTM a Lab Management závisí na definici sestavení jazyka XAML pro automatizaci sestavení, nasazení a testování aplikací.
Sestavení XAML spoléhá na různé konstrukce vytvořené v MTM například testovacím prostředí, testovacích sad a testovacích nastavení a na různých komponent infrastruktury, například řadič sestavení, agenty sestavení, testovacího kontroléru a testovacích agentů k tomuto účelu. Můžete provést stejný pomocí méně kroků pomocí sestavení nebo správy verzí v sadě TFS a Team Services.

| Kroky | S sestavení jazyka XAML | Sestavení nebo Správa verzí |
|-------|----------------------|-----------------|
| Identifikujte počítače k nasazení na sestavení a spuštění testů. | Vytvořte standardní testovací prostředí v MTM s tyto počítače. | není k dispozici |
| Identifikujte testů ke spuštění. | Vytvoření sady testů v MTM, vytvoření testovacích případů a automatizace přidružit každý testovacího případu. Vytvoření nastavení testu v MTM identifikace roli počítačů v testovacím prostředí, ve kterém by měl být spuštěn testy. | Vytvořte automatizované testovací sady v MTM stejným způsobem, pokud máte v úmyslu spravovat testování pomocí testovacích plánů. To můžete přeskočit případně, pokud chcete spustit testy přímo z binárních souborů testovací vyprodukované buildy. Není nutné k vytváření nastavení testů v obou případech. |
| Automatizovat nasazení a testování. | Vytvořte definici sestavení jazyka XAML pomocí LabDefaultTemplate.*.xaml. Zadejte sestavení, sad testů a testovací prostředí v definici sestavení. | Vytvoření [sestavení definice nebo definici verze](https://www.visualstudio.com/team-services/continuous-integration/) s jedno prostředí. Spusťte stejné nasazovací skript (z definice sestavení XAML) pomocí úlohy příkazového řádku a spuštění automatizovaných testů pomocí úloh pro nasazení testovacího agenta a spuštění funkčních testů. Zadejte seznam počítačů a jejich přihlašovacích údajů jako vstupy pro tyto úlohy. |

Mezi výhody používání sestavení nebo Release Management pro tento scénář patří:

* Nepotřebujete řadič sestavení nebo testovací kontroler.
* Testovací agent byl nainstalován prostřednictvím úlohu jako součást sestavení nebo verzi.
* Je snadno přizpůsobit kroky nasazení. Již nejsou omezeny na pomocí jednoho skriptu. Můžete také využít mnoho úloh, které jsou k dispozici v rámci produktu také jako Visual Studio Marketplace.
* Nemáte udržovat testovacích sad. Testy můžete spustit přímo z binárních souborů.
* Získáte bohatší vložené reporting prostředí pro testy, které byly spuštěny v rámci každé sestavení nebo verzi.
* Můžete sledovat, které prostředky (verze, sestavení, pracovních položek, potvrzení) jsou aktuálně nasadila a otestovala na každé prostředí.
* Můžete přizpůsobit a rozšířit automatizace na snadno nasadit pro testovací prostředí s více a to i do produkčního prostředí.
* Můžete naplánovat automatizace provést vždy, když dojde k vrácení se změnami nebo potvrzení, nebo v určitý čas každý den.

<a name="managescvmm"></a>
## <a name="self-service-management-of-scvmm-environments"></a>Samoobslužné služby správu prostředí SCVMM

[Center testovacího prostředí v nástroji Microsoft Test Manager](https://msdn.microsoft.com/library/dd997438.aspx) podporuje možnost spravovat knihovny šablon prostředí a také zřízení prostředí na vyžádání pomocí [SCVMM server](https://technet.microsoft.com/system-center-docs/vmm/vmm).

Samoobslužné zřizování funkce testovacího prostředí centra mít dva odlišné cíle:

* Zadejte jednodušší způsob, jak spravovat infrastrukturu. Mezi příklady infrastruktury správy byly správu šablon virtuálních počítačů a prostředí a automaticky vytvoří soukromých sítích klony prostředí od sebe navzájem izolovat.

* Poskytují jednodušší způsob, jak týmy využívat virtuální počítače v jejich aktivity testování a nasazení. Vytvoření testovacího prostředí, které prostředí přístupné prostřednictvím stejného modelu zabezpečení týmového projektu a integrované použít z těchto virtuálních počítačů v testovací scénáře byly příklady snadné požívání.

Však zadána vývoj bohatší veřejného a soukromého cloudu systémy správy, jako [Microsoft Azure](https://azure.microsoft.com/) a [Microsoft Azure zásobníku](https://azure.microsoft.com/overview/azure-stack/), neexistuje žádný vývoj funkcím pro správu infrastruktury 2017 sady TFS a dále. Místo toho bude pokračovat zaměřuje na snadno spotřebu prostředků, které jsou spravované prostřednictvím těchto cloudových infrastruktur.

Následující tabulka shrnuje typické aktivity, které jste použili k provedení Center testovacího prostředí a způsob jejich pomocí SCVMM nebo Azure (Pokud se jedná o aktivitách řízení infrastruktury) nebo pomocí sady TFS a Team Services provádění (Pokud se test nebo nasazení aktivity):

| Kroky | S centrem testovacího prostředí | Sestavení nebo Správa verzí |
|-------|----------------------|-----------------|
| Spravujte knihovny šablon prostředí. | Vytvořte testovací prostředí. Na virtuálních počítačích nainstalujte potřebný software. Nástroj Sysprep a úložiště v prostředí jako šablona v knihovně. | Pomocí konzoly pro správu SCVMM přímo k vytváření a správě šablon virtuálních počítačů nebo šablony služby. Pokud používáte Azure, vyberte jednu z předem definovaných [šablon Azure Resource Manageru](https://azure.microsoft.com/documentation/templates/) z [Azure Marketplace](https://azure.microsoft.com/marketplace/) nebo z [Azure rychlý start šablony](https://azure.microsoft.com/documentation/templates/). |
| Vytvořte testovací prostředí. | Vyberte šablonu prostředí v knihovně a nasaďte ji. Zadejte potřebné parametry k přizpůsobení konfigurace virtuálních počítačů. | Pomocí konzoly pro správu SCVMM přímo k vytvoření virtuálních počítačů nebo instancí služby ze šablony. Přímo do vytváření prostředků pomocí portálu Azure. Nebo vytvářet verze definice v prostředí. Použití Azure úlohy nebo úlohy z [SCVMM integrace rozšíření](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) k vytvoření nových virtuálních počítačů. Vytvoření nové verze této definice je ekvivalentní k vytvoření nového prostředí v testovacím centru. |
| Připojte k počítačům. | Otevřete v prohlížeči prostředí testovacího prostředí. | Pomocí konzoly pro správu SCVMM přímo se připojit k virtuálním počítačům. Alternativně použijte IP adresy nebo názvy DNS virtuálních počítačů k otevření relace vzdálené plochy. |
| Pořízení kontrolního bodu prostředí nebo obnovit prostředí do čistého kontrolní bod. | Otevřete v prohlížeči prostředí testovacího prostředí. Vyberte možnost k pořízení kontrolního bodu nebo k obnovení do předchozího kontrolního bodu. | Pomocí konzoly pro správu SCVMM přímo k provádění těchto operací na virtuálních počítačích. Nebo, proveďte tyto kroky jako součást větší automatizace, zahrňte kontrolního bodu úlohy z [SCVMM integrace rozšíření](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) v rámci prostředí v definici verze. |

<a name="isolatedenvir"></a>
## <a name="self-service-creation-of-network-isolated-environments"></a>Samoobslužné vytváření síti izolované prostředí

Izolované testovací prostředí sítě je skupina SCVMM virtuálních počítačů, které se dají bezpečně klonovat aniž by to způsobilo sítě je v konfliktu. K tomu bylo potřeba v MTM pomocí řady pokyny, které slouží ke konfiguraci virtuálních počítačů ve veřejné síti sada síťových karet ke konfiguraci virtuálních počítačů v privátní síti a další sadu síťových karet.

S vývoj bohatší veřejného a privátního cloudu systémy správy [Microsoft Azure](https://azure.microsoft.com/) a [Microsoft Azure zásobníku](https://azure.microsoft.com/overview/azure-stack/), můžete více spolehnout na nástroje pro správu cloudu přímo pro podobné Možnosti. Neexistuje žádný způsob ekvivalentní k dosažení tohoto cíle v sestavení a správu verzí.

Doporučujeme, aby zvažte následující možnosti, pokud potřebujete izolace sítě se můžete:

* Jeden motivace pro izolaci sítě bylo snadné konfiguraci více klonech. Každý klonování je repliku přesný původního, názvy počítačů a nastavení konfigurace se zachovají, jako je, a to umožňuje snadno nastavit nové prostředí. Však stejné výhody způsobuje problémy vzniknout později v průběhu životního cyklu (například v produkčním prostředí), protože způsob, jakým jsou nakonec nasazené aplikace není ve stejné. **Místo toho**, zvažte vytvoření nové prostředí stejným způsobem, které jste nastavili produkční a vyhýbat se používání izolace sítě.

* Pomocí infrastruktury veřejného cloudu, jako například [Microsoft Azure](https://azure.microsoft.com/) pro testování potřebuje. Můžete snadno použít [šablon Azure Resource Manageru](https://azure.microsoft.com/documentation/templates/) z [Azure Marketplace](https://azure.microsoft.com/marketplace/) nebo z [Azure rychlý start šablony](https://azure.microsoft.com/documentation/templates/) nastavit skupiny virtuálních počítačů, které jsou připojení prostřednictvím privátní síti a jsou viditelné na veřejné síti jen pomocí proxy serveru nebo jumpbox.
