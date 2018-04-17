---
title: Co&#39;s ve Visual Studio 2015 SDK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: c64aac80-a411-463f-b7bd-8b7607a52ece
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6488f28f2963e17c716c2e9d395ddf77f270e7b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-the-visual-studio-2015-sdk"></a>Co&#39;s ve Visual Studio 2015 SDK
Visual Studio SDK obsahuje následující nové a aktualizované funkce pro Visual Studio 2015, Visual Studio 2015, aktualizovat a Visual Studio 2017.  
  
## <a name="vs-2015-sdk-update-1"></a>VS 2015 SDK Update 1  
 Aktualizace 1 zahrnuje nástrojů, které pomůžou toto rozšíření funkce fungují dobře u barevné motivy a služba bitovou kopii sady Visual Studio.  
  
 Tato témata jsou v části [VSSDK nástroje](../extensibility/internals/vssdk-utilities.md) části:  
  
-   [Nástrojů barev motivů](../extensibility/internals/color-theming-tools.md) vám pomůžou vytvořit a upravit vlastních barev pro sadu Visual Studio.  
  
-   [Nástroje bitových kopií služby](../extensibility/internals/image-service-tools.md) umožňují při práci se soubory manifestu bitovou kopii sady Visual Studio.  
  
## <a name="new-way-to-add-the-visual-studio-sdk-to-visual-studio"></a>Nový způsob přidání sady Visual Studio SDK pro Visual Studio  
 Spouštění v sadě Visual Studio 2015, nepotřebujete samostatně stáhnout sadu Visual Studio SDK. Místo toho můžete jej nainstalovat jako součást procesu instalace normální nebo můžete k její instalaci později. Při otevírání nebo vytvořte VSIX řešení, Visual Studio zobrazí výzvu k instalaci sady Visual Studio Extensibility Tools. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="new-ways-of-creating-extensions"></a>Nové způsoby vytváření rozšíření  
 Od verze Visual Studio 2015 SDK, máte různé možnosti pro vytvoření rozšíření, v závislosti na programovací jazyk, který používáte.  
  
### <a name="visual-c-and-visual-basic"></a>Visual C# a Visual Basic  
 Pro C# a Visual Basic je plný rozsah šablony položek projektu, které vám umožní vytvořit VSPackages, příkazy nabídky, nástroj windows, editor třídění, editor vylepšení a rozšíření okraj editoru. Můžete přidat některé nebo všechny tyto standardní projekt VSIX. Další informace naleznete v tématu:  
  
-   [Vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   [Vytváření rozšíření pomocí panelu nástrojů](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   [Vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   [Vytváření rozšíření pomocí VSPackage](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
     Průvodce VSPackage už vytvoří rozšíření v C# nebo Visual Basic.  
  
### <a name="c"></a>C++  
 Pro jazyk C++ průvodce VSPackage podporovat příkazy nabídky okna nástrojů a vlastní editory. Podívejte se v **nový projekt** dialogové okno ve **Visual C++ / rozšiřitelnost**.  
  
## <a name="vs-sdk-reference-assemblies-via-nuget"></a>Sestavení referenční VS SDK prostřednictvím balíčku NuGet  
 Pro vyšší přenositelnost a sdílení rozšiřitelnost projektů můžete použít referenční sestavení VS SDK verze NuGet.  Jsou dostupné v [nuget.org](http://www.nuget.org) publikováno [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) a lze je snadno přidat na projekt nebo řešení pomocí sady Visual Studio **odkazuje / spravovat NuGet Balíčky** dialogové okno. Můžete přidat jednotlivé odkazy na konkrétní rozšíření sestavení nebo přidat VS SDK odkazuje na sestavení najednou pomocí sady SDK VS [Meta balíček](http://www.nuget.org/packages/VSSDK_Reference_Assemblies). Další informace o systému NuGet najdete v tématu [NuGet dokumentace](/NuGet) a [uživatelského rozhraní Správce balíčků](/NuGet/Tools/Package-Manager-UI) témata.  
  
 Použijete-li verze NuGet referenční sestavení VS SDK, jiný uživatel nebude muset nainstalovat VS SDK k otevření a sestavení projektu.  NuGet referenční sestavení a nástroje pro sestavení VS SDK se automaticky nainstalují na svém počítači pro tento projekt.  
  
 Šablony položek VS SDK použijte NuGet pro jejich odkazy a nástroje pro vytváření, získáte výhody NuGet ve výchozím nastavení.  
  
> [!NOTE]
>  Můžete nadále používat referenční sestavení VS SDK, které jsou nainstalované s projekty (umístěné v \<umístění instalovat Visual Studio > \ VSSDK\VisualStudioIntegration\Common\Assemblies) a existující projekty rozšíření nemusíte být upgradovat na balíčky NuGet.  Projekt **odkazuje / přidat odkaz** dialogu budou nadále používat referenční sestavení VS SDK nainstalována.  
>   
>  Pokud chcete upravit existující projekty použít NuGet, najdete v článku [postup: migrace VSPackages Visual Studio 2015](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md) jehož oddíl na aktualizace rozšiřitelnost projektů na balíčky NuGet.  
  
## <a name="light-bulbs"></a>Žárovek  
 Většina zajímavé nové způsoby zápisu rozšíření kódu jsou poskytovány Roslyn projektu. Další informace najdete v tématu [Roslyn](https://github.com/dotnet/Roslyn).  
  
 Žárovek jsou nové funkce, která se dodává s verzí VSSDK. Jsou ikony používané v editoru Visual Studio, které rozbalte zobrazíte sadu kódu refaktoringu akce nebo opravy problémů se identifikovanou pomocí analyzátorů předdefinované kódu. Další informace najdete v tématu [návod: zobrazení návrhy žárovky](../extensibility/walkthrough-displaying-light-bulb-suggestions.md).  
  
## <a name="updated-user-experience-guidelines"></a>Aktualizované prostředí pro práci uživatelů  
 Navrhování nová rozšíření nebo funkce pro sadu Visual Studio? Podívejte se na aktualizovanou a rozšířená [Visual Studio prostředí pro práci uživatelů](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  Zjistíte [barvu tokeny](../extensibility/ux-guidelines/shared-colors-for-visual-studio.md), [velikosti písem](../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md), [dialogové okno rozložení specifikace](../extensibility/ux-guidelines/layout-for-visual-studio.md)a další pokyny, budete muset bezproblémově integrovat nové uživatelské rozhraní pomocí sady Visual Studio.