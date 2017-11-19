---
title: "Řešení a projektů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 10/5/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.addnewsolutionitem
- vs.environment.projects
- vs.openproject
- vs.addnewitem
- vs.addexistingitem
- VS.SolutionExplorer
- vs.newproject
- vs.addexistingsolutionitem
- vs.environment.solutions
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solution items, folder in Solution Explorer
- solution items, shared
- solutions [Visual Studio]
- project items [Visual Studio], about project items
- solutions [Visual Studio], designing
- projects [Visual Studio]
- solutions [Visual Studio], projects and
- projects [Visual Studio], setting up
ms.assetid: aeaf56cb-c2dd-47f6-b012-23b84b7a7254
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca3094b3bfe35381236798164fa18e58304bae3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="solutions-and-projects-in-visual-studio"></a>Řešení a projekty v sadě Visual Studio
Když vytvoříte aplikaci, web, modul plug-in, atd. v sadě Visual Studio spustíte s *projektu*. V logických smysl projekt obsahuje všechny soubory zdrojového kódu, ikony, obrázky, datové soubory a cokoliv jiného, co se zkompiluje do spustitelný program, nebo web, jinak je potřeba, aby bylo možné provést kompilace. Projekt obsahuje také všechna nastavení kompilátoru a ostatní konfigurační soubory, které mohou být potřebné různé služby nebo součásti, které komunikovat s vaším programem.  

> [!NOTE]
>  Nemusíte používat řešení nebo projekty, pokud nechcete. Jednoduše můžete otevřít soubory do sady Visual Studio a začít upravovat kód. V tématu [vývoj kódu v sadě Visual Studio bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) Další informace.  

Soubor projektu (.vbproj, .csproj, VCXPROJ) je soubor XML, který definuje virtuální složky hierarchii společně s cesty pro všechny položky v projektu. Obsahuje taky nastavení sestavení. Pokud chcete zobrazit obsah souboru projektu, můžete vyberte název projektu v Průzkumníku řešení a zvolte **uvolnit projekt** z nabídky kontextu (klikněte pravým tlačítkem). Pak znovu otevřete kontextu nabídku a vyberte **upravit \<projectname\>**.  

V sadě Visual Studio je soubor projektu vrstva Průzkumníku řešení používá pro zobrazení obsahu projektu a nastavení. Při kompilaci projektu nástroje MSBuild modul využívá soubor projektu pro vytvoření spustitelného souboru. Můžete také upravit projekty k vytvoření jiné druhy výstup.  

Projekt je obsažené, v logické smysl a v systému souborů, v *řešení*, který může obsahovat jednu nebo více souvisejících s projekty, společně s informacemi o sestavení, Visual Studio okna nastavení a všechny ostatní soubory, které nejsou související s konkrétní projekt. Řešení je popsán textový soubor (.sln) s svůj vlastní jedinečný formát; Obecně není určen k provádění úprav ručně.  

Řešení má přidruženou *.suo* soubor, který ukládá nastavení, předvoleb a informace o konfiguraci pro každý uživatel, který pracoval na projekt.  

 Následující diagram znázorňuje vztah mezi projekty a řešení a položky, které logicky obsahují.  

 ![Projekty Visual Studio a řešení](../ide/media/vside-project-diagram.png)  

## <a name="creating-new-projects"></a>Vytváření nových projektů  
 Nejjednodušší způsob, jak vytvořit nový projekt je spuštění z šablony projektu, který se skládá ze základní sady souborů předem generovaného kódu, konfigurační soubory, prostředky a nastavení, které vám pomůžou začít vytváření konkrétního typu aplikace nebo webu v konkrétní programovací jazyk. Tyto šablony jsou, co se zobrazí v **nový projekt** nebo **nový web** dialogové okno když zvolíte **soubor**, **nový**,  **Projekt** nebo **soubor**, **nové**, **webu**. Další informace najdete v tématu [vytváření řešení a projekty](../ide/creating-solutions-and-projects.md).  

Můžete také vytvořit vlastní šablony projektů a položek. Další informace najdete v tématu [vytváření projektů a šablon položek](../ide/creating-project-and-item-templates.md).  

## <a name="managing-projects-in-solution-explorer"></a>Správa projektů v Průzkumníku řešení  
 Když vytvoříte nový projekt, můžete použít **Průzkumníku řešení** zobrazení a správa projektů a řešení a jejich přidružené položky. Následující obrázek znázorňuje Průzkumníku řešení s řešením C#, který obsahuje dva projekty.  

 ![Průzkumník řešení](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")  

## <a name="in-this-section"></a>V tomto oddílu  

-   [Vytváření řešení a projektů](../ide/creating-solutions-and-projects.md)  

-   [Přidávání a odebírání položek projektu](../ide/adding-and-removing-project-items.md)  

-   [Správa vlastností projektů a řešení](../ide/managing-project-and-solution-properties.md)  

-   [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)  

-   [Vlastnosti aplikace](../ide/application-properties.md)  

-   [Správa sestavení a podepsání manifestu](../ide/managing-assembly-and-manifest-signing.md)  

-   [Postupy: určení aplikace Iicon (Visual Basic, C#)](../ide/how-to-specify-an-application-icon-visual-basic-csharp.md)  

-   [Cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md)  

-   [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  

## <a name="see-also"></a>Viz také  
 [Integrované vývojové prostředí sady Visual Studio](../ide/visual-studio-ide.md)
