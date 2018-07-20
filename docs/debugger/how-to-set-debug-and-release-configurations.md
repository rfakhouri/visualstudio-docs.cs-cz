---
title: Nastavení ladění a vydání konfigurace | Dokumentace Microsoftu
ms.custom: ''
ms.date: 04/10/2017
ms.technology: vs-ide-debug
ms.topic: reference
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
ms.openlocfilehash: ea27fdccaadc70f22d9c9c02d75ddef98a11be13
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153095"
---
# <a name="set-debug-and-release-configurations-in-visual-studio"></a>Nastavení ladění a vydání konfigurace v sadě Visual Studio
Projekty aplikace Visual Studio mají samostatné verze a ladění konfigurace pro váš program. Jak naznačují názvy, sestavení verze ladění pro ladění a verze vydání pro konečnou distribuci vydání.  
  
Konfigurace ladění programu je kompilován sestaví neoptimalizovaná a obsahující symbolické ladicí informace. Optimalizace komplikuje ladění, protože vztah mezi zdrojovým kódem a vytvořenými pokyny je složitější.  
  
Konfigurace programu pro vydání neobsahuje žádné symbolické ladicí informace a je plně optimalizována. Ladit informace mohou být generovány v souborech PDB [v závislosti na možnostech kompilátoru](#BKMK_symbols_release) , která se používají. Vytváření souborů PDB může být velmi užitečné, pokud budete muset později ladit vydané verze.  
  
Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
Můžete změnit konfiguraci sestavení z **sestavení** nabídky, z panelu nástrojů nebo na stránkách vlastností projektu. Stránky vlastností projektu jsou specifické pro jazyk. Následující postup ukazuje, jak změnit konfiguraci sestavení z nabídky a panelu nástrojů. Další informace o tom, jak změnit konfiguraci sestavení v projektech v jiných jazycích najdete v následující části Viz také.  
  
## <a name="change-the-build-configuration"></a>Změňte konfiguraci buildu  
  
1.  Z **sestavení** nabídce vyberte možnost **nástroje Configuration Manager**a pak vyberte **ladění** nebo **vydání**.  
  
2.  Na panelu nástrojů zvolte buď **ladění** nebo **vydání** z **konfigurace řešení** pole se seznamem.  
  
     ![konfigurace sestavení nástrojů](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     Tento panel nástrojů není k dispozici ve verzích Express. Můžete použít **sestavit řešení F6** a **zahájit ladění F5** položky nabídky pro výběr konfigurace.

## <a name="BKMK_symbols_release"></a>Generovat soubory symbolů (PDB) pro sestavení

Pro většinu typů projektu soubory s příponou .pdb jsou generovány ve výchozím nastavení pro obě ladění a sestavení pro vydání, ale výchozí nastavení se liší v závislosti na konkrétním projektu typu a verzi sady Visual Studio. Můžete nakonfigurovat, zda kompilátor generuje soubory PDB a jaký druh ladicí informace, včetně.

> [!IMPORTANT] 
> Ladicí program načte pouze soubor PDB pro spustitelný soubor, který přesně odpovídá souboru .pdb vytvořeném, když byl sestaven spustitelný soubor (to znamená, že PDB musí být originál nebo kopie původního souboru .pdb). Další informace najdete v části [proč sada Visual Studio vyžaduje soubory symbolů ladicího programu shodovaly binárním souborům, se kterými byly vytvořeny?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

Každý typ projektu může mít jiný způsob nastavení těchto možností.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>Generovat soubory symbolů pro projekt C#, ASP.NET nebo Visual Basic

Podrobné informace o nastavení projektu pro konfiguraci ladění v jazyce C# najdete v tématu [nastavení pro konfiguraci ladění jazyka C# projektu](../debugger/project-settings-for-csharp-debug-configurations.md). V jazyce Visual Basic naleznete v tématu [v tomto tématu](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).

1. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **vlastnosti**.

2. Zvolte **vydání** nebo **ladění** sestavení z **konfigurace** seznamu.

2. Zvolte **sestavení** nastavení a pak klikněte na tlačítko **Upřesnit** tlačítko.

    V jazyce Visual Basic, zvolte **kompilaci** nastavení a **Upřesnit možnosti kompilace** tlačítko místo.

3. Zvolte **úplné**, **přenosné**, nebo **pdb_only** v **ladicí informace** pole se seznamem (**Generovat ladicí informace** v jazyce Visual Basic).

    Přenosný formát je nejnovější formát pro různé platformy pro .NET Core. Další informace o možnostech najdete v tématu [dialogové okno Upřesnit nastavení sestavení (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md).

    ![Generování souborů PDB pro sestavení v jazyce C#](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

4. Sestavte projekt.

    Soubory symbolů vytvořené ve stejné složce jako spustitelný soubor nebo hlavního výstupního souboru.

### <a name="generate-symbol-files-for-a-c-project"></a>Generovat soubory symbolů pro projekt jazyka C++

1. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a zvolte **vlastnosti**.

2. Zvolte **vydání** nebo **ladění** sestavení z **konfigurace** seznamu.

2. V části **Linkeru > ladění**, vyberte požadované možnosti pro **Generovat ladicí informace**.

    Podrobné informace o nastavení projektu pro konfiguraci ladění v jazyce C++, naleznete v tématu [nastavení pro konfiguraci ladění jazyka C++ projektu](../debugger/project-settings-for-a-cpp-debug-configuration.md).

4. Konfigurace možností pro vygenerování souborů databáze programu

    Ve většině projektů C++, výchozí hodnota je `$(OutDir)$(TargetName).pdb`, který generuje soubory PDB do výstupní složky.

    ![Generování souborů PDB pro sestavení v jazyce C++](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus") 

5. Sestavte projekt.

    Soubory symbolů vytvořené ve stejné složce jako spustitelný soubor nebo hlavního výstupního souboru.
  
## <a name="see-also"></a>Viz také  
 [Zadejte soubory symbolů (PDB) a zdrojových souborů v ladicím programu sady Visual Studio](../debugger/debugger-settings-and-preparation.md)  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Nastavení projektu pro jazyk C# konfiguraci ladění](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Konfigurace ladění projektu v jazyce Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Postupy: Vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md)
