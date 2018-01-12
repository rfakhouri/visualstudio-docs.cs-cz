---
title: "Spolupráce na vývoji řešení pro systém Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3b69eccc3f6c140c44bff3b2d3d24e33914cae84
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="collaborative-development-of-office-solutions"></a>Spolupráce na vývoji řešení pro systém Office
  Více vývojářů může pracovat na Microsoft Office project stejným způsobem, který budou spolupracovat na jiných projektů sady Visual Studio. Visual Studio správně vyhledá instalaci sady Microsoft Office na každém počítači, i v případě Office je nainstalována v různých umístěních. Existují však některé důležité informace znát.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="debug-properties-are-not-shared"></a>Ladění není sdílejí vlastnosti  
 Ladění vlastnosti nejsou sdílí několik uživatelů v rámci správy zdrojového kódu. Projekty Visual Basic a Visual C# uložit ladění vlastnosti v souboru konkrétního uživatele (*ProjectName*. vbproj.user nebo *ProjectName*. csproj.user), a tento soubor není ve správě zdrojového kódu. Pokud je ladění víc než jedna osoba, každou osobu, musíte zadat vlastnosti ladění ručně.  
  
 Pokud projekt nachází ve sdílené síťové složce místo ve správě zdrojového kódu, některými dalšími kroky, musí přesměrováni na povolení spolupráce vývojáři otevřete řešení a otestovat sestavení.  
  
## <a name="source-control-requires-checking-out-all-files"></a>Správa zdrojového kódu vyžaduje rezervování všechny soubory  
 Pokud používáte zdrojového kódu pro projekty, přečtěte si nejprve všechny soubory v souboru kódu v **Průzkumníku řešení** (například soubory kódu ThisDocument, ThisWorkbook nebo ThisAddIn) pokaždé, když změníte souboru kódu i v soubory, které jsou skryté. ve výchozím nastavení. Pokud je rezervován pouze soubor nejvyšší úrovně kódu, vaše změny mohou být ztraceny.  
  
 Když provedete změny, zkontrolujte, že všechny soubory ve zpět. Další informace o souborech skrytá kódu v projektech, najdete v části [projektech pro systém Office v prostředí sady Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="security-for-informal-collaboration-on-a-network"></a>Zabezpečení pro neformální spolupráce v síti  
 Pro všechna řešení na úrovni dokumentu, které se nacházejí v umístění v síti (například \\ \\ *Servername*\\*Sharename*), plně kvalifikovaný umístění musí být přidaný do seznam důvěryhodných složek v aplikaci Microsoft Office, které pracujete s. Vyberte možnost Zahrnout podadresáře v hlavní složce nebo konkrétně přidat ladění a složky do seznamu důvěryhodných složky sestavení. Další informace o tom, jak to udělat najdete v tématu [udělení vztah důvěryhodnosti s dokumenty](../vsto/granting-trust-to-documents.md).  
  
 Dočasné certifikáty, které jsou automaticky generovány v okamžiku sestavení nejsou zabezpečeny nástrojem hesla. Certifikáty obsahovat přihlašovací jméno pro vývojáře a jiné osobní informace. Pokud nasadíte vlastní nastavení, které jsou podepsány dočasné certifikáty, ostatní pravděpodobně moci přistupovat k těmto informacím.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Sestavování řešení pro systém Office](../vsto/building-office-solutions.md)  
  
  