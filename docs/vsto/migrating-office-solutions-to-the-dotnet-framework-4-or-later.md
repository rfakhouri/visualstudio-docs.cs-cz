---
title: Migrace řešení Office na rozhraní .NET Framework 4 nebo novější
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 729fafd1f6dfdf889293c9686f455be8de5a81fc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970371"
---
# <a name="migrate-office-solutions-to-the-net-framework-4-or-later"></a>Migrace řešení Office na rozhraní .NET Framework 4 nebo novější
  Pokud cílové rozhraní projektu pro Office se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později z dřívější verze rozhraní .NET Framework, některé další kroky může být požádán o nadále spouštět řešení v počítači vývoje a koncových uživatelů. Další informace najdete v tématu [požadované změny pro spouštění projektů Office migrovaných na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).

 Kromě toho může už kompilaci projektu. Některé funkce projektech pro systém Office mají různé programovací modely pro různé verze rozhraní .NET Framework. Když se změní cílovou architekturu projektu aplikace Office na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo ze starší verze rozhraní .NET Framework, musíte později provést následující změny kódu, do projektu:

- [Aktualizace projektů Excel a Word, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

- [Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](/visualstudio/vsto/update-ribbon-customizations-in-office-projects-to-migrate-to-dotnet-framework-4-or-4-5)

- [Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

  Cílové rozhraní projektu pro Office se změní při upgradu tohoto projektu ze starší verze sady Visual Studio. Další informace najdete v tématu [Upgrade a migrace řešení Office](../vsto/upgrading-and-migrating-office-solutions.md).

  Další informace o tom, proč některé funkce v projektech pro systém Office mají různé programovací model, při cílení [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později, naleznete v tématu [změny v návrhu projektů Office cílených na rozhraní .NET Framework 4 nebo .NET Framework 4.5](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md) a [Visual Studio Tools for Office runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).

## <a name="see-also"></a>Viz také:
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
- [Postupy: Cílení na určitou verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md)
- [Řešení potíží s chybami v řešeních pro systém Office](../vsto/troubleshooting-errors-in-office-solutions.md)
- [Další podpora pro chyby v řešeních pro systém Office](../vsto/additional-support-for-errors-in-office-solutions.md)
