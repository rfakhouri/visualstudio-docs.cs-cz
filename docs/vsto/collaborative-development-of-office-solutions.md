---
title: Spolupráce na vývoji řešení pro systém Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 76c26a110d88d3dee8bf7540647ea0bfde4e7c4f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635056"
---
# <a name="collaborative-development-of-office-solutions"></a>Spolupráce na vývoji řešení pro systém Office
  Více vývojářů může pracovat na projektu pro Office v stejně, jako jsou spolupráce na jiné projekty sady Visual Studio. Visual Studio správně vyhledá instalace Microsoft Office na každém počítači i v případě Office je nainstalovaná v různých umístěních. Existují však některé důležité informace, je potřeba vědět.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="debug-properties-are-not-shared"></a>Ladění se nesdílejí vlastnosti
 Ladit vlastnosti nejsou sdílí několik uživatelů pod správou zdrojových kódů. Visual Basic a Visual C# projekty uložit vlastnosti ladění do souboru konkrétního uživatele (*ProjectName*. vbproj.user nebo *ProjectName*. csproj.user), a tento soubor není pod správou zdrojových kódů . Pokud je ladění více než jednou osobou, každý uživatel, který musíte zadat vlastnosti ladění ručně.

 V případě, že projekt je umístěno do sdílené síťové složky místo ve správě zdrojového kódu, několik kroků navíc musí přesměrováni k povolení spolupráce vývojářům otevřete řešení a testovací sestavení.

## <a name="source-control-requires-checking-out-all-files"></a>Správa zdrojů vyžaduje nástroj rezervuje se všechny soubory
 Pokud používáte správy zdrojového kódu pro projekty, měli byste zkontrolovat všechny soubory v souboru kódu v **Průzkumníka řešení** (například *ThisDocument*, *ThisWorkbook*, nebo *ThisAddIn* soubory kódu) pokaždé, když změníte soubor kódu, dokonce i soubory, které jsou ve výchozím nastavení skrytá. Pokud rezervovat pouze soubor kódu nejvyšší úrovně mohou být změny ztraceny.

 Když provedete změny, zkontrolujte, zda že všechny soubory ve zpět. Další informace o souborech skryté kód v projektech, naleznete v tématu [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).

## <a name="security-for-informal-collaboration-on-a-network"></a>Zabezpečení pro spolupráci neformálních v síti
 Pro všechna řešení na úrovni dokumentu, které jsou v umístění v síti (například \\ \\ *Servername*\\*Sharename*), plně kvalifikované umístění musí být přidané do seznam důvěryhodných složek v aplikaci Microsoft Office, které pracujete. Vyberte možnost zahrnout podsložky ve složce hlavní nebo konkrétně přidat ladění a vytvoření složky do seznamu důvěryhodných složek. Další informace o tom, jak to provést, najdete v části [udělit důvěryhodnost dokumenty](../vsto/granting-trust-to-documents.md).

 Dočasné certifikáty, které jsou automaticky generovány v okamžiku sestavení nejsou zabezpečeny nástrojem hesla. Certifikáty obsahovat přihlašovací jméno pro vývojáře a jiné osobní informace. Pokud nasazujete přizpůsobení, které jsou podepsány certifikáty dočasné, jiná můžou být schopni přistupovat k těmto informacím.

## <a name="see-also"></a>Viz také:
- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
- [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)
