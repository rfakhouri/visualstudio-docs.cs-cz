---
title: "Kompilaci a sestavování v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 29101e8e82fa9babf553be17414f1330cd6f7e18
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="compiling-and-building-in-visual-studio"></a>Kompilaci a sestavování v sadě Visual Studio

Spuštění sestavení vytvoří sestavení a spustitelný soubor aplikace z vašeho zdrojového kódu v libovolném bodě během cyklu vývoje. Proces sestavení je obecně velmi podobný napříč mnoha různých typech projektů jako Windows, ASP.NET, mobilní aplikace a dalších. Proces sestavení je velmi podobný také napříč programovacích jazyků, například C#, Visual Basic, C++ a F #. 

Podle často sestavování svého kódu, můžete rychle identifikovat chyby při kompilaci, jako je například nesprávná syntaxe, překlepu klíčová slova a neshody typu. Můžete také rychle zjistit a opravit chyby, jako je například logika a sémantických, často vytváření a ladění verzemi kód.  

Úspěšném sestavení je v podstatě ověření, že zdrojový kód aplikace obsahuje správnou syntaxi a všechny statické odkazy na knihovny, sestavení a další součásti byly vyřešeny. Tímto se vytvoří spustitelný soubor aplikace, která může být testována pak pro správné fungování v obou [ladění prostředí](../debugger/index.md) a prostřednictvím řady různých ruční a automatické testy na [ověření kvality kódu](../test/improve-code-quality.md). Po aplikace plně otestovala, můžete pak zkompilovat verzi k nasazení na vašich zákazníků. Úvod do tohoto procesu, najdete v části [návod: vytváření aplikace](../ide/walkthrough-building-an-application.md).  

V rámci řada produktů Visual Studio, existují tři metody, které můžete použít k vytvoření aplikace: Visual Studio IDE, nástroje příkazového řádku nástroje MSBuild a Team Foundation Build na Visual Studio Team Services:
 
| Metoda sestavení | Výhody | 
| --- |--- | --- |  
| IDE – integrované vývojové prostředí |-Vytvořit sestavení okamžitě a otestovat ve ladicí program.<br />-Spuštění více procesorů sestavení pro projekty C++ a C#.<br />-Přizpůsobte různé aspekty systému sestavení. |
| Příkazový řádek nástroje MSBuild| -Projekty sestavení bez instalace sady Visual Studio.<br />-Spuštění více procesorů sestavení pro všechny typy projektů.<br />-Přizpůsobte většině oblastí systém sestavení.|
| Sestavení Team Foundation | -Automatizaci procesu sestavení jako součást nepřetržité integrace/průběžné doručování kanálu.<br />-Použijte automatizovaných testů s každou sestavení.<br />-Použít prakticky neomezené prostředky na základě může pro procesy sestavení.<br />-Upravte sestavení pracovního postupu a vytvořit sestavení aktivity hluboko přizpůsobené úkoly.|  

Dokumentaci v této části přejde na další informace o procesu sestavení na základě IDE. Další informace o dalších metodách v tématu [MSBuild](../msbuild/msbuild.md) a [průběžnou integraci a nasazení](https://www.visualstudio.com/docs/build/overview), v uvedeném pořadí.

## <a name="overview-of-building-from-the-ide"></a>Přehled vytváření z prostředí IDE  

Při vytváření projektu sady Visual Studio vytvoří výchozí konfigurace sestavení projektu a řešení, které obsahuje projektu.  Tyto konfigurace definovat, jak jsou vytvořené a nasazené řešení a projekty. Konfigurace projektu zejména jsou jedinečné pro cílové platformy (například Windows pr Linux) a vytvořit typ (například ladění nebo verze). Můžete upravit tyto konfigurace však a můžete také vytvořit vlastní konfigurace, podle potřeby.

První Úvod do vytváření v prostředí IDE, najdete v části [návod: vytváření aplikace](walkthrough-building-an-application.md).  

Dále zde naleznete [sestavování a čištění projektů a řešení v sadě Visual Studio](building-and-cleaning-projects-and-solutions-in-visual-studio.md) Další informace o různých aspektech přizpůsobení můžete provést proces. Přizpůsobení zahrnují [změna výstupního adresáře](how-to-change-the-build-output-directory.md), [zadání vlastní události sestavení](specifying-custom-build-events-in-visual-studio.md), [Správa závislosti projektu](how-to-create-and-remove-project-dependencies.md), [Správa sestavení protokolu soubory](how-to-view-save-and-configure-build-log-files.md), a [potlačení upozornění kompilátoru](how-to-suppress-compiler-warnings.md).

Odtud můžete prozkoumat celou řadu dalších úloh:
- [Pochopení konfigurace sestavení](understanding-build-configurations.md)
- [Principy platforem sestavení](understanding-build-platforms.md)
- [Správa vlastností projektů a řešení](managing-project-and-solution-properties.md).  
- Určení událostí sestavení v [C#](how-to-specify-build-events-csharp.md) a [jazyka Visual Basic](how-to-specify-build-events-visual-basic.md). 
- [Nastavení možností sestavení](reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Vytvářet více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).  
  
## <a name="see-also"></a>Viz také  

- [Vytvoření (kompilace) webové projekty](http://msdn.microsoft.com/Library/a9cbb88c-8fff-4c67-848b-98fbfd823193)   
