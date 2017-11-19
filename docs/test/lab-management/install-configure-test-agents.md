---
title: "Instalace a konfigurace testovacích agentů | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: configure test agents, test lab
ms.assetid: EBAA2E04-A97A-4047-B739-8DBA7F2D5074
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: fdcca04c9dd06132496912f4df30e3d86d24d42a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="install-and-configure-test-agents"></a>Instalace a konfigurace testovacích agentů

Pro testovací scénáře s využitím sady Visual Studio a Visual Studio Team Services nebo Team Foundation Server (TFS) nebude nutné testovací kontroler, protože agentů pro Microsoft Visual Studio zpracování orchestration komunikaci se službou Team Services nebo TFS. Například máte spuštěný průběžné testování s vaší sestavení a verzí pracovních postupů v Team Services nebo TFS.

Pokud potřebujete agentem test agent nebo testovací kontroler pracovat se sadou TFS 2013, použijte agentů pro Microsoft Visual Studio 2013 Update 5 a nakonfigurujte testovací kontroler.

Zvažte také, pokud by bylo snazší [použijte raději sestavení nebo Release Management](use-build-or-rm-instead-of-lab-management.md).

## <a name="what-do-i-need"></a>Co musím udělat?

**Kde získat testovací kontroler a testovací agenti?**

* Pokud používáte systém testů pomocí úlohy vNext sestavení a chcete nainstalovat agenty z místního adresáře- 

  * [Stáhněte agenta pro sadu Microsoft Visual Studio 2015 RTM a Update 1](http://go.microsoft.com/fwlink/p/?LinkId=619266). 

  * [Stáhněte agenta pro Microsoft Visual Studio 2017 a Visual Studio 2015 Update 2](https://www.visualstudio.com/downloads/download-visual-studio-vs) – zvolte **nástrojů pro Visual Studio 2015** a pak vyberte **agentů pro Visual Studio 2015** vlevo navigační panel.

* [Stáhněte agenta pro Microsoft Visual Studio 2013 Update 5](http://go.microsoft.com/fwlink/p/?LinkId=619264), pokud chcete spustit:

  * Spouštění testů pomocí místní vzdáleného počítače.

  * Souvislý testy vzdáleně pomocí nástroje Microsoft Test Manager nebo Mstestu a testovací nastavení pro testovací prostředí.

  * Průběžné testů pomocí sady TFS 2013.

Tato instalační programy jsou k dispozici jako soubory ISO (virtuální disk CD-ROM) Snadná instalace na virtuálních počítačích. 

[Můžete kombinovat verzí sady TFS, Microsoft Test Manager, testovacího kontroléru a agenta test?](#MixedVersions)

**Jaké požadavky na systém je nutné nainstalovat Moje testovací kontrolery a testovací agenty?**

| Položka | Požadavky |
| ---- | ------------ |
| **Agent** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows XP Service Pack 3<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **Řadiče** | Windows 10<br />Windows 8, Windows 8.1<br />Windows 7 Service Pack 1<br />Windows Server 2012, Windows Server 2012 R2<br />Windows Server 2008 Release 2, Service Pack 1 |
| **.NET Framework** | .NET Framework 4.5 |

## <a name="q--a"></a>Dotazy a odpovědi

<!-- BEGINSECTION class="m-qanda" -->

<a name="MixedVersions"></a>

####<a name="q-can-i-mix-versions-of-tfs-microsoft-test-manager-the-test-controller-and-test-agent"></a>Otázka: je možné kombinovat verzí sady TFS, Microsoft Test Manager, testovacího kontroléru a agenta test?

Odpověď: Ano, zde jsou kompatibilní a podporované kombinace:

| SADY TFS | Nástroje Microsoft Test Manager s testovacím Center | Řadiče | Agent |
| --- | -------------------------------------- | ---------- | ----- |
| 2015: upgrade z 2013 | 2013 | 2013 |2013 |
| 2015: nové instalace | 2013 | 2013 | 2013 |
| 2015: upgrade z 2013 nebo s novou instalací | 2015 | 2013 | 2013 |
| 2013 | 2015 | 2013 | 2013 |

####<a name="q-will-the-test-agent-2015-support-all-the-scenarios-supported-by-test-controller-and-test-agent-of-visual-studio-2013"></a>Otázka: bude 2015 agenta Test podporovat všechny scénáře podporované testovacího Kontroléru a Test Agent nástroje Visual Studio 2013?

Odpověď: doporučujeme, abyste že se používá agentů pro Visual Studio všechny nové automatizované testování scénáře. Můžete nasadit agenty testovací úlohy v definici sestavení ke stažení a instalaci testovacích agentů v počítači.
Následující tabulka uvádí scénáře podporované agenti pro Visual Studio 2013 a alternativ pro Team Foundation Server (TFS) 2015 a Team Services (TS).

| Scénáře podporované agenti pro Visual Studio 2013 | Alternativní v sadě TFS a TS |
| --- | --- |
| Pracovního postupu sestavení-nasazení-testování v sadě Visual Studio | Uživatelé mohou používat [sestavení definice](https://www.visualstudio.com/team-services/continuous-integration/) (ne sestavení XAML) pro sestavení, nasazení a testovací scénáře v sadě TFS. |
| Zatížení testování (testování výkonu) pomocí místní vzdáleného počítače | Použijte testovací řadiče a testovací agenty 2013 Update 5 ke spuštění zatížení testy na místě. [Další informace](https://msdn.microsoft.com/en-us/library/ff400223.aspx). |
| Vzdálené spuštění automatizovaných testů z použití testovacího prostředí v nástroji Microsoft Test Manager | Aktuálně neexistuje žádné alternativní pro tento scénář. Doporučujeme použít úlohou pro spuštění funkčních testů v sestavení a verze definice (není v jazyce XAML sestavení) provést testy vzdáleně. |
| Vývojáři provádění vzdáleného testů v sadě Visual Studio | Již není podporována. |

<!-- ENDSECTION -->

## <a name="see-also"></a>Viz také

* [Nastavení počítačů a shromažďování diagnostických informací s použitím nastavení testu](https://msdn.microsoft.com/library/dd286743%28v=vs.140%29.aspx)
