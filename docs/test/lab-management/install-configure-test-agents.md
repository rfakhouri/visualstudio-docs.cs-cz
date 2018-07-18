---
title: Instalace testovacích agentů a kontrolerů testů
ms.date: 07/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- configure test agents, test lab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8914b6b876b27b94add446a627087fb34e5082ea
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2018
ms.locfileid: "37890406"
---
# <a name="install-test-agents-and-test-controllers"></a>Instalace testovacích agentů a kontrolerů testů

Pro testovací scénáře, které používají Visual Studio a Visual Studio Team Services (VSTS) nebo Team Foundation Server (TFS) nemusíte testovacího kontroléru. Agents pro Visual Studio zpracování orchestraci komunikací s VSTS nebo sady TFS. Scénář může být spuštění průběžné testů pro sestavení a vydání pracovní postupy ve VSTS a TFS.

Můžete taky zvážit, pokud je vhodnější použít [sestavení nebo Správa vydaných verzí](use-build-or-rm-instead-of-lab-management.md) namísto správy testovacího prostředí.

## <a name="system-requirements"></a>Požadavky na systém

| Položka | Požadavky |
| ---- | ------------ |
| **Agent** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2016 Standard a Datacenter<br />Windows Server 2012, Windows Server 2012 R2 |
| **Kontroler** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2016 Standard a Datacenter<br />Windows Server 2012, Windows Server 2012 R2 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="install-the-test-controller-and-test-agents"></a>Nainstalujte testovací kontrolér a testovací agenty

Můžete si stáhnout agenty pro Visual Studio 2017 z [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?q=agents). Přejděte do dolní části stránky a vyhledejte *Agents for Visual Studio 2017*. Vyberte buď *agenta* nebo *řadič*a klikněte na tlačítko *Stáhnout*. Spouštění staženého spustitelného souboru k instalaci testovacího agenta nebo kontroler.

Agenty si můžete stáhnout pro Visual Studio 2015 a Visual Studio 2013 z [starší soubory ke stažení](https://visualstudio.microsoft.com/vs/older-downloads/) stránky.

Tyto instalační programy jsou dostupné jako soubory ISO pro snadnou instalaci na virtuálních počítačích.

## <a name="compatible-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>Kompatibilní verze serveru TFS, Microsoft Test Manager, testovacího kontroléru a testovacího agenta

Podle následující tabulky můžete kombinovat různé verze TFS, Microsoft Test Manager (MTM), testovacího kontroléru a testovacího agenta:

| TFS | MTM s centra testovacích prostředí | Kontroler | Agent |
| --- | -------------------------------------- | ---------- | ----- |
| 2017: upgrade z 2015 nebo s novou instalací | 2017 | 2017 | 2017 |
| 2017: upgrade z 2015 nebo s novou instalací | 2017 | 2013 update 5 | 2013 update 5 |
| 2017: upgrade z 2015 nebo s novou instalací | 2015 | 2013 update 5 | 2013 update 5 |
| 2015: upgrade z 2013 | 2013 | 2013 |2013 |
| 2015: nové instalace | 2013 | 2013 | 2013 |
| 2015: upgrade z 2013 nebo s novou instalací | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

## <a name="upgrade-from-visual-studio-2013-test-agents"></a>Upgrade z Visual Studio 2013 testovacích agentů

Doporučujeme použít produkt agents for Visual Studio ve všech nových scénářích automatizované testování. Můžete použít *nasadit testovací agenti* úkol v definici sestavení stáhnout a nainstalovat testovací agenty na svém počítači.

Následující tabulka uvádí scénáře, podporuje Agents for Visual Studio 2013 a možnosti pro Team Foundation Server (TFS) 2015 a VSTS:

| Agents for Visual Studio 2013 podporuje scénáře | Alternativní v TFS a VSTS |
| --- | --- |
| Pracovní postup sestavení-nasazení-testování v sadě Visual Studio | Uživatelé můžou použít [definice sestavení](/vsts/build-release/) (ne sestavení XAML) pro sestavení, nasazení a testování scénářů v sadě TFS. |
| Zátěžové testování (testování výkonu) pomocí místní vzdálené počítače | Použít testovací Kontrolér a testovací agenty 2013 Update 5 spustit zátěžové testy místně. |
| Vzdálené spuštění automatizovaných testů z nástroje Microsoft Test Manager pomocí testovacího prostředí | Aktuálně neexistuje žádná alternativa pro tento scénář. Doporučujeme, abyste pomocí úlohy pro spuštění funkčních testů v buildu a definice verzí (ne v sestavení XAML) Chcete-li vzdáleně spustit testy. |
| Vývojáři provádění vzdáleného testů v sadě Visual Studio | Již nejsou podporovány. |
