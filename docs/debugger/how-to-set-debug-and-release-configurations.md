---
title: 'Postupy: nastavení ladění a vydání konfigurace | Microsoft Docs'
ms.custom: H1HackMay2017
ms.date: 04/10/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.builds
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ae43c5cab67d79450cea1dc024da98fe25c5375
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34690663"
---
# <a name="how-to-set-debug-and-release-configurations-in-visual-studio"></a>Postupy: nastavení ladění a vydání konfigurace v sadě Visual Studio
Projekty Visual Studio mít samostatné verze a konfigurace pro váš program ladění. Jak je určeno, názvy, sestavení ladicí verze pro ladění a vydání verze pro distribuci finální verzi.  
  
Konfigurace ladění vašeho programu je kompilovat s úplné symbolické ladicí informace a žádná optimalizace. Optimalizace komplikuje, ladění, protože je složitější vztah mezi zdrojového kódu a vygenerovaný pokyny.  
  
Konfigurace verze vašeho programu neobsahuje informace o symbolické ladicí a je plně optimalizovaná. Ladění informace může být generována v soubory PDB [v závislosti na možnosti kompilátoru](#BKMK_symbols_release) které se používají. Vytváření soubory PDB může být velmi užitečná, pokud později musíte ladit prodejní verzi.  
  
Další informace o konfiguracích sestavení najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
Můžete změnit konfiguraci sestavení z **sestavení** nabídky panelu nástrojů nebo na stránkách vlastností projektu. Stránky vlastností projektu jsou specifické pro jazyk. Následující postup ukazuje, jak změnit konfiguraci sestavení z nabídky a panelu nástrojů. Další informace o tom, jak změnit konfiguraci sestavení v projektech v různých jazycích najdete v části Viz také níže.  
  
## <a name="change-the-build-configuration"></a>Změnit konfiguraci sestavení  
  
1.  Z **sestavení** nabídce vyberte možnost **nástroje Configuration Manager**, pak vyberte **ladění** nebo **verze**.  
  
2.  Na panelu nástrojů vyberte buď **ladění** nebo **verze** z **konfigurace řešení** pole se seznamem.  
  
     ![konfigurace sestavení nástrojů](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     Tento panel nástrojů není k dispozici v edicích Express. Můžete použít **sestavení řešení F6** a **F5 spusťte ladění** položky nabídky zvolte konfigurace.

## <a name="BKMK_symbols_release"></a>Generování souborů symbolu (.pdb) pro sestavení

U většiny typů projektu soubory PDB se generují ve výchozím nastavení pro obě ladění a sestavení pro vydání, ale výchozí nastavení se liší v závislosti na typu vaše konkrétní projektu a verzi sady Visual Studio. Můžete nakonfigurovat jestli kompilátor generuje soubory PDB a jaký druh informací ladění zahrnout.

> [!IMPORTANT] 
> Ladicí program načte pouze soubor PDB pro spustitelný soubor, který přesně odpovídá souboru .pdb vytvořeném, když byl sestaven spustitelný soubor (to znamená, že PDB musí být originál nebo kopie původního souboru .pdb). Další informace najdete v části [proč Visual Studio vyžaduje ladicí program symbol soubory tak, aby přesně shodu binární soubory, které byly vytvořeny ve?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

Každý typ projektu, může mít jiný způsob nastavení těchto možností.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>Generovat soubory symbolů pro projekt C#, ASP.NET nebo Visual Basic

Podrobné informace o nastavení projektu pro konfiguraci ladění v jazyce C#, najdete v části [projektu nastavení pro konfiguraci ladění jazyka C#](../debugger/project-settings-for-csharp-debug-configurations.md). V jazyce Visual Basic, najdete v části [v tomto tématu](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).

1. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **vlastnosti**.

2. Vyberte **verze** nebo **ladění** sestavit z **konfigurace** seznamu.

2. Zvolte **sestavení** nastavení a klikněte **Upřesnit** tlačítko.

    V jazyce Visual Basic, vyberete **zkompilovat** nastavení a **Upřesnit možnosti kompilace** tlačítko místo.

3. Zvolte **úplné**, **přenosné**, nebo **pdb_only** v **ladicí informace** pole se seznamem (**Generovat ladicí informace** v jazyce Visual Basic).

    Přenosné formát je nejnovější formát a platformy .NET Core. Další informace o možnostech najdete v tématu [dialogové okno Upřesnit nastavení sestavení (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md).

    ![Generovat soubory PDB pro sestavení v jazyce C#](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

4. Sestavte projekt.

    Symbol soubory vytvořeny ve stejné složce jako spustitelný soubor nebo hlavní výstupní soubor.

### <a name="generate-symbol-files-for-a-c-project"></a>Generovat soubory symbolů pro projektu jazyka C++

1. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **vlastnosti**.

2. Vyberte **verze** nebo **ladění** sestavit z **konfigurace** seznamu.

2. V části **Linkeru > ladění**, vyberte požadované možnosti pro **Generovat ladicí informace**.

    Podrobné informace o nastavení projektu pro konfiguraci ladění v jazyce C++ najdete v tématu [projektu nastavení pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md).

4. Konfigurace možností pro generování soubory programu databáze

    Ve většině projekty C++, výchozí hodnota je `$(OutDir)$(TargetName).pdb`, který generuje soubory PDB do výstupní složky.

    ![Generovat soubory PDB pro sestavení v jazyce C++](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus") 

5. Sestavte projekt.

    Symbol soubory vytvořeny ve stejné složce jako spustitelný soubor nebo hlavní výstupní soubor.
  
## <a name="see-also"></a>Viz také  
 [Zadejte soubory symbolu (.pdb) a zdrojových souborů v aplikaci Visual Studio ladicí program](../debugger/debugger-settings-and-preparation.md)  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Konfigurace ladění nastavení projektu pro jazyk C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Nastavení projektu jazyka Visual Basic konfiguraci ladění](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)
