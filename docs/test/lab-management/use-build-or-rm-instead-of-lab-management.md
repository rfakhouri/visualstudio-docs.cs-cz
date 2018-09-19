---
title: Použití správy sestavení nebo vydaných verzí pro automatizované testování
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
ms.openlocfilehash: a5896eccbee65450ab6206dd26a8f76d3fc48d5c
ms.sourcegitcommit: b9a32c3d94b19e7344f4872bc026efd3157cf220
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135599"
---
# <a name="use-azure-test-plans-instead-of-lab-management-for-automated-testing"></a>Pomocí testovacích plánů Azure namísto správy testovacího prostředí pro automatizované testování

Pokud používáte Microsoft Test Manager (MTM) a správa testovacího prostředí pro automatizované testování nebo pro automatizaci sestavení nasazení testování, toto téma vysvětluje, jak lze dosáhnout pomocí stejné cíle [sestavení a vydání](/azure/devops/pipelines/index?view=vsts) funkcí v produktu Team Foundation Server (TFS) a plány testování v Azure.

## <a name="build-deploy-test-automation"></a>Automatizace sestavení nasazení testování

MTM a správa testovacího prostředí závisí na definici sestavení XAML pro automatizaci sestavení, nasazení a testování vašich aplikací. Sestavení XAML závisí na různých konstrukcí vytvořené v nástroji MTM, jako je například testovací prostředí, testovací sady a testovací nastavení a na různých komponent infrastruktury, například kontroler sestavení, agentů sestavení, testovacího kontroléru a testovacích agentů k dosažení tohoto cíle. Můžete provést stejný menším počtem kroků s pomocí sestavení nebo správy vydaných verzí v TFS a kanály Azure.

| Kroky | Sestavení XAML | Build nebo Release Management |
|-------|----------------------|-----------------|
| Identifikujte počítače k nasazení na sestavení a spuštění testů. | Vytvořte Standardní laboratorní prostředí v nástroji MTM se tyto počítače. | není k dispozici |
| Identifikace testů ke spuštění. | Vytvoření testovací sady v nástroji MTM, vytvořit testovací případy a přidružení automatizace k jednotlivým testovacím případům. Vytvoření nastavení testu v nástroji MTM identifikace role počítačů v testovacím prostředí, ve kterém se mají spustit testy. | Vytvořte automatizované testovací sady v nástroji MTM stejným způsobem Pokud budete chtít spravovat testování pomocí testovacích plánů. To můžete přeskočit případně, pokud chcete spouštět testy přímo z vytvářené buildy binárních souborů testu. Není nutné k vytvoření nastavení testu v obou případech. |
| Automatizaci nasazení a testování. | Vytvoření definice sestavení XAML pomocí LabDefaultTemplate.*.xaml. Zadejte sestavení, testovací sady a testovací prostředí v definici sestavení. | Vytvoření [sestavení a kanál verze](/azure/devops/pipelines/index?view=vsts) se pro jedno prostředí. Spusťte stejný skript nasazení (z definice sestavení XAML), pomocí příkazového řádku úkolu a spuštění automatizovaných testů pomocí úlohy nasazení testovacího agenta a spuštění funkčních testů. Zadejte seznam počítačů a jejich pověření jako vstupy pro tyto úlohy. |

Zde jsou některé z výhod používání Build nebo Release Management pro tento scénář:

* Nepotřebujete řadič sestavení nebo testovacího kontroléru.
* Testovací agent se instaluje prostřednictvím úkolu jako součást sestavení nebo vydané verzi.
* Je snadné k přizpůsobení kroků nasazení. Už nejsou omezené na pomocí jednoho skriptu. Můžete taky využít výhod celé řadě úloh, které jsou dostupné v produktu stejně jako v aplikaci Visual Studio Marketplace.
* Není nutné udržovat testovací sady. Testy můžete spustit přímo z binárních souborů.
* Můžete získat bohatší vložených sestav prostředí pro testy, které byly spuštěny v rámci každého sestavení nebo vydané verzi.
* Můžete sledovat, které prostředky (verze, sestavení, pracovních položek, potvrzení) jsou aktuálně nasadila a otestovala v každém prostředí.
* Můžete přizpůsobit a rozšířit automatizace snadno nasazovat do více testovacích prostředích a dokonce i do produkčního prostředí.
* Můžete naplánovat, automatizace, která se provede při každém vrácení se změnami nebo potvrzení změn, nebo v určitý čas každý den.

## <a name="self-service-management-of-scvmm-environments"></a>Samoobslužná správa prostředí SCVMM

[Centra testů v nástroji Microsoft Test Manager](/azure/devops/test/mtm/guidance-mtm-usage?view=vsts) podporuje možnost Spravovat knihovnu šablon prostředí, stejně jako zřizovat prostředí na vyžádání pomocí [serveru SCVMM](/system-center/vmm/overview?view=sc-vmm-1801).

Samoobslužné zřizování funkce centra testovacích prostředí mají dva různé cíle:

* Poskytují jednodušší způsob, jak spravovat infrastrukturu. Správa šablon virtuálních počítačů a prostředí a soukromých sítích klony prostředí od sebe navzájem izolovat se automaticky vytvoří byly příklady na správu infrastruktury.

* Poskytují jednodušší způsob pro týmy, které využívají virtuální počítače v jejich aktivity testování a nasazení. Vytváření testovacích prostředí přístupné prostřednictvím stejného modelu zabezpečení projektu a integrované pomocí těchto virtuálních počítačů v testovacích scénářů byly příklady využití jednoduché.

Ale vzhledem vývoj bohatší veřejného a soukromého cloudu systémy pro správu, jako [Microsoft Azure](https://azure.microsoft.com/) a [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/), neexistuje žádný vývoj funkcí správy infrastruktury v TFS 2017 a novější. Místo toho soustředit na snadné požívání prostředky spravované přes tyto cloudových infrastruktur pokračuje.

Následující tabulka shrnuje typické aktivit, které provedete v centra testovacích prostředí a jak je pomocí SCVMM nebo v Azure (v případě, že jsou aktivity správy infrastruktury) nebo pomocí serveru TFS a služby Azure DevOps můžete provést (Pokud se test nebo nasazení aktivity):

| Kroky | Pomocí centra testovacích prostředí | Build nebo Release Management |
|-------|----------------------|-----------------|
| Spravujte knihovnu šablon prostředí. | Vytvoření testovacího prostředí. Na virtuálních počítačích nainstalujte potřebný software. Nástroj Sysprep a úložiště prostředí jako šablonu do knihovny. | Pomocí konzoly pro správu SCVMM přímo k vytváření a správě šablon virtuálních počítačů nebo šablon služeb. Pokud používáte Azure, vyberte jednu z [šablony rychlý start Azure](https://azure.microsoft.com/resources/templates/). |
| Vytvoření testovacího prostředí. | Vyberte šablonu prostředí v knihovně a nasaďte ji. Zadejte potřebné parametry k přizpůsobení konfigurace virtuálních počítačů. | Přímo k vytvoření virtuálních počítačů nebo instancí služby ze šablon pomocí konzoly pro správu SCVMM. Přímo k vytváření prostředků pomocí webu Azure portal. Nebo vytvořte definici vydané verze v prostředí. Použití Azure úlohy nebo úlohy z [rozšíření integrace SCVMM](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) k vytvoření nových virtuálních počítačů. Vytváří se nová verze této definice je ekvivalentní k vytváření nových prostředí v centru testovacího prostředí. |
| Připojení k počítačům. | Otevřete testovací prostředí v prohlížeči prostředí. | Přímo se připojit k virtuálním počítačům pomocí konzoly pro správu SCVMM. Alternativně otevřete relací vzdálené plochy pomocí IP adresy nebo názvy DNS virtuálních počítačů. |
| Kontrolní bod prostředí nebo obnovit prostředí na vyčištění kontrolní bod. | Otevřete testovací prostředí v prohlížeči prostředí. Vyberte možnost k pořízení kontrolního bodu nebo obnovení na dřívější kontrolní bod. | Pomocí konzoly pro správu SCVMM přímo k provedení těchto operací na virtuálních počítačích. Nebo provádět tyto kroky jako součást větší automatizace zahrnout úkoly kontrolního bodu z [rozšíření SCVMM integrace](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) jako součást prostředí v definici vydané verze. |

## <a name="create-network-isolated-environments"></a>Vytvoření prostředí izolované sítě

Síťovém prostředí izolované testovací prostředí je skupina virtuálních počítačů v SCVMM, které lze bezpečně klonovat, aniž by vznikly konflikty v síti. To bylo provedeno v MTM řada pokynů, které používá sadu síťových karet ke konfiguraci virtuálních počítačů v privátní síti a další sadu síťových karet ke konfiguraci virtuálních počítačů ve veřejné síti.

Však testovací plány Azure a sadou TFS v kombinaci s SCVMM sestavit a úloha nasazení, slouží ke správě prostředí SCVMM, zřízení izolované virtuální sítě a implementace sestavení nasazení testování scénářů. Například můžete použít na úlohy:

* Vytvoření, obnovení a odstraňte kontrolní body
* Vytvoření nových virtuálních počítačů pomocí šablony
* Spuštění a zastavení virtuálních počítačů
* Spustit vlastní skripty prostředí PowerShell pro SCVMM

Další informace najdete v tématu [vytvořit virtuální prostředí izolované sítě pro scénáře sestavení nasazení testování](/azure/devops/pipelines/targets/create-virtual-network?view=vsts).
