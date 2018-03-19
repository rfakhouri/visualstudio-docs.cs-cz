---
title: "Nainstalujte testovacích agentů a testovací kontrolery pro sadu Visual Studio | Microsoft Docs"
ms.date: 03/02/2018
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- configure test agents, test lab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4eaba4be128042776382d63d1b0198a48cecef94
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="install-test-agents-and-test-controllers"></a>Nainstalujte testovacích agentů a testovací kontrolery

Testovací scénáře, které používají Visual Studio a Visual Studio Team Services (VSTS) nebo Team Foundation Server (TFS) není nutné testovací kontroler. Agenti pro sadu Visual Studio zpracování orchestration komunikaci s služby VSTS nebo TFS. Scénáři může být spuštění průběžné testů pro sestavení a verze pracovních postupů v služby VSTS nebo TFS.

Také můžete zvážit, pokud je vhodnější použít [sestavení nebo Správa verzí](use-build-or-rm-instead-of-lab-management.md) místo lab management.

## <a name="system-requirements"></a>Požadavky na systém

| Položka | Požadavky |
| ---- | ------------ |
| **Agent** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows XP Service Pack 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **Řadiče** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="install-the-test-controller-and-test-agents"></a>Nainstalujte testovací kontrolery a testovací agenti

Můžete si stáhnout agentů pro Visual Studio 2017 z [visualstudio.com](https://www.visualstudio.com/downloads/?q=agents). Přejděte do dolní části stránky a vyhledejte *agentů pro Visual Studio 2017*. Vyberte buď *agenta* nebo *řadič*a potom zvolte *Stáhnout*. Spusťte stažený spustitelný soubor instalace zařízení nebo testovacího agenta.

Agenty si můžete stáhnout pro Visual Studio 2015 a Visual Studio 2013 z [starší stahování](https://www.visualstudio.com/vs/older-downloads/) stránky.

Tato instalační programy jsou k dispozici jako soubory ISO Snadná instalace na virtuálních počítačích.

## <a name="compatible-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>Kompatibilní verze sady TFS, Microsoft Test Manager, testovacího kontroléru a agenta test

Podle následující tabulky můžete kombinovat různé verze sady TFS, Microsoft Test Manager (MTM), testovací kontroler a agenta test:

| TFS | MTM s testovacím Center | Řadiče | Agent |
| --- | -------------------------------------- | ---------- | ----- |
| 2017: upgrade z 2015 nebo s novou instalací | 2017 | 2017 | 2017 |
| 2017: upgrade z 2015 nebo s novou instalací | 2017 | 2013 Update 5 | 2013 Update 5 |
| 2017: upgrade z 2015 nebo s novou instalací | 2015 | 2013 Update 5 | 2013 Update 5 |
| 2015: upgrade z 2013 | 2013 | 2013 |2013 |
| 2015: nové instalace | 2013 | 2013 | 2013 |
| 2015: upgrade z 2013 nebo s novou instalací | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

## <a name="upgrade-from-visual-studio-2013-test-agents"></a>Upgrade z Visual Studio 2013 testovacích agentů

Doporučujeme, abyste použili agentů pro sadu Visual Studio všechny nové automatizované testování scénáře. Můžete použít *nasadit testovací agenty* úloh v definici sestavení ke stažení a instalaci testovacích agentů v počítači.

Následující tabulka uvádí scénáře podporované agentů pro Visual Studio 2013 a alternativy pro Team Foundation Server (TFS) 2015 a služby VSTS:

| Scénáře podporované agenti pro Visual Studio 2013 | Alternativní v sadě TFS a služby VSTS |
| --- | --- |
| Pracovního postupu sestavení-nasazení-testování v sadě Visual Studio | Uživatelé mohou používat [sestavení definice](/vsts/build-release/) (ne sestavení XAML) pro sestavení, nasazení a testovací scénáře v sadě TFS. |
| Zatížení testování (testování výkonu) pomocí místní vzdáleného počítače | Použití testovacího Kontroléru a testovací agenty 2013 Update 5 spustit zatížení testy místně. |
| Vzdálené spuštění automatizovaných testů z použití testovacího prostředí v nástroji Microsoft Test Manager | Aktuálně neexistuje žádné alternativní pro tento scénář. Doporučujeme použít úlohou pro spuštění funkčních testů v sestavení a verze definice (není v jazyce XAML sestavení) provést testy vzdáleně. |
| Vývojáři provádění vzdáleného testů v sadě Visual Studio | Již není podporována. |
