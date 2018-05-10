---
title: ID úlohy a součást Visual Studio 2017 nástroje pro sestavení
description: Použít identifikátory pracovního vytížení a součást Visual Studio k vytvoření aplikace klasické založené na systému Windows
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 05/07/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload:
- multiple
ms.openlocfilehash: 8634017862a12b3a399f003d6f16c9689b7aaa20
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio 2017 nástroje pro sestavení součástí adresáře

Tabulky v tomto seznamu stránky ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat v závislosti na manifestu VSIX. Všimněte si, že přidáme další součásti, jako jsme vydání aktualizace pro Visual Studio.

Všimněte si také následující stránka:

* Každé zatížení má vlastní části, a potom podle ID úlohy a tabulku součásti, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **požadované** součásti se nainstalují při instalaci zatížení.
* Pokud zvolíte možnost, můžete taky nainstalovat **doporučeno** a **volitelné** součásti.
* Přidali jsme také oddíl, který uvádí další součásti, které nejsou spojit s jakoukoli úlohu.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. K určení závislostí naše minimální součástí použijte tabulky na této stránce. V některých případech to může znamenat, že zadáváte pouze jedna součást z pracovního vytížení. V jiných scénářích může znamenat, že zadáváte více součástí z jediné úlohy nebo více součástí z více úloh. Další informace najdete v tématu [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak používat tyto identifikátory najdete v tématu [pomocí parametrů příkazového řádku pro instalaci Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam úloh a ID součástí pro ostatní produkty, naleznete v části [zatížení 2017 Visual Studio a ID součástí](workload-and-component-ids.md) stránky.

## <a name="azure-development-build-tools"></a>Vývoj pro Azure sestavovací nástroje

**ID:** Microsoft.VisualStudio.Workload.AzureBuildTools

**Popis:** MSBuild úlohy a cíle pro vytváření aplikací Azure.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Nástroje pro vývoj rozhraní .NET framework 4.6.1 | 15.7.27520.0 | Požadováno
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Nástroje pro tvorbu Azure | 15.0.26621.2 | Požadováno
Microsoft.VisualStudio.Component.Azure.ClientLibs | Knihovny Azure pro .NET | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Nástroje služby Azure Cloud sestavení | 15.7.27617.1 | Požadováno
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Nástroje pro vývoj kontejneru – nástroje pro sestavení | 15.7.27617.1 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | Sestavení vývojářských nástrojů WCF | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Nástroje pro sestavení vývoj pro web | 15.7.27604.0 | Požadováno
Microsoft.Net.Component.4.5.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.1 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.2 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.TargetingPack | Cílení na pack rozhraní .NET framework 4.5 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.6.TargetingPack | Cílení na pack rozhraní .NET framework 4.6. | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.TargetingPack | Cílení na pack rozhraní .NET framework 4 | 15.6.27406.0 | Doporučeno
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Nástroje pro vývoj rozhraní .NET framework 4 – 4.6 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Core.Component.SDK | Nástroje pro vývoj .NET core 2.0 | 15.6.27406.0 | Doporučeno
Microsoft.VisualStudio.Component.AspNet45 | Pokročilé funkce ASP.NET | 15.7.27625.0 | Doporučeno
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | Doporučeno
Microsoft.Net.Component.3.5.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 3.5 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.SDK | Rozhraní .NET framework 4.6.2 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.SDK | Rozhraní .NET framework 4.7.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.TargetingPack | Rozhraní .NET framework 4.7.1 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.SDK | Rozhraní .NET framework 4.7 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.TargetingPack | Rozhraní .NET framework 4.7 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | Nástroje pro vývoj 4.7.1 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Nástroje pro vývoj 4.7 rozhraní .NET framework | 15.6.27406.0 | Nepovinné

## <a name="net-desktop-build-tools"></a>Nástroje plochy sestavení rozhraní .NET

**ID:** Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools

**Popis:** nástroje pro vytváření grafického subsystému WPF Windows Forms a konzolové aplikace pomocí jazyka C#, Visual Basic a F #.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno
Microsoft.Component.ClickOnce.MSBuild | Nástroje pro sestavení ClickOnce | 15.7.27617.1 | Doporučeno
Microsoft.Net.Component.4.5.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.1 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.2 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.TargetingPack | Cílení na pack rozhraní .NET framework 4.5 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.6.TargetingPack | Cílení na pack rozhraní .NET framework 4.6. | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.TargetingPack | Cílení na pack rozhraní .NET framework 4 | 15.6.27406.0 | Doporučeno
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Nástroje pro vývoj rozhraní .NET framework 4 – 4.6 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Core.Component.SDK | Nástroje pro vývoj .NET core 2.0 | 15.6.27406.0 | Doporučeno
Microsoft.VisualStudio.Component.TestTools.BuildTools | Testovací nástroje pro základní funkce – nástroje pro sestavení | 15.7.27625.0 | Doporučeno
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | Sestavení vývojářských nástrojů WCF | 15.6.27309.0 | Doporučeno
Microsoft.Net.Component.3.5.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 3.5 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.SDK | Rozhraní .NET framework 4.6.2 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.SDK | Rozhraní .NET framework 4.7.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.TargetingPack | Rozhraní .NET framework 4.7.1 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.SDK | Rozhraní .NET framework 4.7 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.TargetingPack | Rozhraní .NET framework 4.7 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | Nástroje pro vývoj 4.7.1 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Nástroje pro vývoj 4.7 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.Core.Component.SDK.1x | Nástroje pro vývoj 1.0 1.1 základní rozhraní .NET | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.FSharp.MSBuild | kompilátor jazyka F# | 15.7.27604.0 | Nepovinné

## <a name="msbuild-tools"></a>Nástroje MSBuild

**ID:** Microsoft.VisualStudio.Workload.MSBuildTools

**Popis:** poskytuje nástroje potřebné k vytvoření aplikace založené na MSBuild.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.VisualStudio.Component.CoreBuildTools | Základní nástroje sestavení sady Visual Studio | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno

## <a name="net-core-build-tools"></a>Nástroje pro sestavení .NET core

**ID:** Microsoft.VisualStudio.Workload.NetCoreBuildTools

**Popis:** nástroje pro vytváření aplikací pomocí .NET Core, ASP.NET Core, HTML/JavaScript a kontejnery.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | Nástroje pro vývoj .NET core 2.0 | 15.6.27406.0 | Požadováno
Microsoft.NetCore.BuildTools.ComponentGroup | Nástroje pro sestavení .NET core | 15.7.27617.1 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.Net.Core.Component.SDK.1x | Nástroje pro vývoj 1.0 1.1 základní rozhraní .NET | 15.6.27406.0 | Nepovinné

## <a name="nodejs-build-tools"></a>Nástroje pro sestavení Node.js

**ID:** Microsoft.VisualStudio.Workload.NodeBuildTools

**Popis:** vytvářet škálovatelné síťové aplikace pomocí Node.js, asynchronní runtime jazyka JavaScript založeného na událostech.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Node.Build | Podpora Node.js | 15.6.27406.0 | Požadováno

## <a name="officesharepoint-build-tools"></a>Nástroje sestavení sady Office nebo služby SharePoint

**ID:** Microsoft.VisualStudio.Workload.OfficeBuildTools

**Popis:** sestavení Office a SharePoint doplňky a doplňků VSTO.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.ClickOnce.MSBuild | Nástroje pro sestavení ClickOnce | 15.7.27617.1 | Požadováno
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.Net.Component.4.5.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.2 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.5.TargetingPack | Cílení na pack rozhraní .NET framework 4.5 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.TargetingPack | Cílení na pack rozhraní .NET framework 4 | 15.6.27406.0 | Požadováno
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Nástroje pro vývoj rozhraní .NET framework 4.6.1 | 15.7.27520.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet | Správce balíčků NuGet | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.Sharepoint.BuildTools | Nástroje sestavení sady Office nebo SharePoint vývoj | 15.7.27617.1 | Požadováno
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | Sestavení vývojářských nástrojů WCF | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Nástroje pro sestavení vývoj pro web | 15.7.27604.0 | Požadováno
Microsoft.VisualStudio.Component.TeamOffice.BuildTools | Nástroje sestavení Visual Studio Tools pro sadu Office (VSTO) | 15.7.27617.1 | Doporučeno
Microsoft.Net.Component.4.6.2.SDK | Rozhraní .NET framework 4.6.2 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.SDK | Rozhraní .NET framework 4.7.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.TargetingPack | Rozhraní .NET framework 4.7.1 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.SDK | Rozhraní .NET framework 4.7 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.TargetingPack | Rozhraní .NET framework 4.7 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | Nástroje pro vývoj 4.7.1 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Nástroje pro vývoj 4.7 rozhraní .NET framework | 15.6.27406.0 | Nepovinné

## <a name="universal-windows-platform-build-tools"></a>Univerzální platforma Windows sestavovací nástroje

**ID:** Microsoft.VisualStudio.Workload.UniversalBuildTools

**Popis:** poskytuje nástroje potřebné k vytváření aplikací pro univerzální platformu Windows.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | Požadováno
Microsoft.Component.VC.Runtime.OSSupport | Visual C++ runtime pro UPW | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.7.1.SDK | Rozhraní .NET framework 4.7.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statické analytické nástroje | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Tools.ARM | Kompilátory jazyka Visual C++ a knihovny pro ARM | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 verze 15.7 v14.14 nejnovější v141 nástroje | 15.7.27625.0 | Požadováno
Microsoft.VisualStudio.ComponentGroup.UWP.BuildTools | Univerzální platforma Windows sestavení požadavky | 15.7.27703.1 | Požadováno
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.7.27703.1 | Doporučeno
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 SDK (10.0.15063.0) pro UPW: C#, VB, JS | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 SDK (10.0.16299.0) pro UPW: C#, VB, JS | 15.6.27406.0 | Nepovinné

## <a name="visual-c-build-tools"></a>Nástroje sestavení sady Visual C++

**ID:** Microsoft.VisualStudio.Workload.VCTools

**Popis:** sestavení aplikací klasické pracovní plochy Windows pomocí sady nástrojů Microsoft C++, ATL a MFC.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statické analytické nástroje | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Nástroje sestavení Visual C++ pro základní funkce | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Aktualizace Visual C++ 2017 Redistributable | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 verze 15.7 v14.14 nejnovější v141 nástroje | 15.7.27625.0 | Požadováno
Microsoft.VisualStudio.Component.Windows10SDK | Prostředí Windows Universal C Runtime | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.TestTools.BuildTools | Testovací nástroje pro základní funkce – nástroje pro sestavení | 15.7.27625.0 | Doporučeno
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.7.27703.1 | Doporučeno
Microsoft.Component.VC.Runtime.UCRTSDK | Sady Windows Universal CRT SDK | 15.6.27309.0 | Nepovinné
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.140 | Sada nástrojů v14.00 (v140) VC ++ 2015.3 pro plochu | 15.7.27617.1 | Nepovinné
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL pro x86 a x64 | 15.7.27625.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.ATLMFC | Visual C++ MFC pro x86 a x64 | 15.7.27625.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI podpory | 15.6.27309.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | Moduly pro standardní knihovny (experimentální) | 15.6.27309.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.Tools.ARM | Kompilátory jazyka Visual C++ a knihovny pro ARM | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Kompilátory jazyka Visual C++ a knihovny pro ARM64 | 15.6.27309.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 SDK (10.0.15063.0) pro plochy C++ [x86 a x64] | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 SDK (10.0.15063.0) pro UPW: C#, VB, JS | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 SDK (10.0.15063.0) pro UPW: C++ | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 SDK (10.0.16299.0) pro plochy C++ [x86 a x64] | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 SDK (10.0.16299.0) pro UPW: C#, VB, JS | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 SDK (10.0.16299.0) pro UPW: C++ | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.Component.WinXP | Podpora Windows XP pro C++ | 15.7.27703.1 | Nepovinné
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK a sadu SDK UCRT | 15.6.27406.0 | Nepovinné
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | Podpora Windows XP pro C++ | 15.7.27703.1 | Nepovinné

## <a name="web-development-build-tools"></a>Nástroje pro sestavení vývoj pro web

**ID:** Microsoft.VisualStudio.Workload.WebBuildTools

**Popis:** úlohy nástroje MSBuild a cíle pro vytvoření webové aplikace.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Nástroje pro vývoj rozhraní .NET framework 4.6.1 | 15.7.27520.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | Nástroje pro sestavení vývoj pro web | 15.7.27604.0 | Požadováno
Microsoft.Component.ClickOnce.MSBuild | Nástroje pro sestavení ClickOnce | 15.7.27617.1 | Doporučeno
Microsoft.Net.Component.4.5.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.1 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.2 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.5.TargetingPack | Cílení na pack rozhraní .NET framework 4.5 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.6.TargetingPack | Cílení na pack rozhraní .NET framework 4.6. | 15.6.27406.0 | Doporučeno
Microsoft.Net.Component.4.TargetingPack | Cílení na pack rozhraní .NET framework 4 | 15.6.27406.0 | Doporučeno
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Nástroje pro vývoj rozhraní .NET framework 4 – 4.6 | 15.6.27406.0 | Doporučeno
Microsoft.Net.Core.Component.SDK | Nástroje pro vývoj .NET core 2.0 | 15.6.27406.0 | Doporučeno
Microsoft.VisualStudio.Component.AspNet45 | Pokročilé funkce ASP.NET | 15.7.27625.0 | Doporučeno
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Nástroje pro vývoj kontejneru – nástroje pro sestavení | 15.7.27617.1 | Doporučeno
Microsoft.VisualStudio.Component.TestTools.BuildTools | Testovací nástroje pro základní funkce – nástroje pro sestavení | 15.7.27625.0 | Doporučeno
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK | 15.0.27617.1 | Doporučeno
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | Sestavení vývojářských nástrojů WCF | 15.6.27309.0 | Doporučeno
Microsoft.Net.Component.3.5.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 3.5 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.SDK | Rozhraní .NET framework 4.6.2 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.6.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.SDK | Rozhraní .NET framework 4.7.1 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.1.TargetingPack | Rozhraní .NET framework 4.7.1 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.SDK | Rozhraní .NET framework 4.7 SDK | 15.6.27406.0 | Nepovinné
Microsoft.Net.Component.4.7.TargetingPack | Rozhraní .NET framework 4.7 cílení pack | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Nástroje pro vývoj rozhraní .NET framework 4.6.2 | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | Nástroje pro vývoj 4.7.1 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Nástroje pro vývoj 4.7 rozhraní .NET framework | 15.6.27406.0 | Nepovinné
Microsoft.Net.Core.Component.SDK.1x | Nástroje pro vývoj 1.0 1.1 základní rozhraní .NET | 15.6.27406.0 | Nepovinné

## <a name="mobile-development-with-net"></a>Mobilní vývoj pomocí rozhraní .NET

**ID:** Microsoft.VisualStudio.Workload.XamarinBuildTools

**Popis:** nástroje pro vytváření aplikací a platformy pro iOS, Android a Windows pomocí jazyka C# a F #.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet cílů a úloh sestavení | 15.0.26919.1 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno
Component.JavaJDK | Java SE Development Kit (8.0.1120.15) | 15.6.27406.0 | Doporučeno
Component.Android.SDK25 | Instalační program Android SDK (API úrovně 25) | 15.6.27413.0 | Nepovinné

## <a name="unaffiliated-components"></a>Nezávislou na komponenty

Toto jsou součásti, které nejsou součástí žádné úlohy, ale může být vybraný jako jednotlivé součásti.

ID součásti | Název | Version
--- | --- | ---
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27520.0
Microsoft.VisualStudio.Component.VC.ATL.ARM | Visual C++ ATL pro ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM.Spectre | Visual C++ ATL pro ARM s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64 | Visual C++ ATL pro ARM64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64.Spectre | Visual C++ ATL pro ARM64 s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.Spectre | Visual C++ ATL (x86/x64) s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATLMFC.Spectre | Visual C++ MFC pro x86 nebo x64 s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (experimentální) | 15.7.27520.0
Microsoft.VisualStudio.Component.VC.MFC.ARM | Visual C++ MFC pro ARM | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM.Spectre | Visual C++ MFC pro ARM s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64 | Visual C++ MFC pro ARM64 | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64.Spectre | Visual C++ MFC podpora ARM64 s jejich spektrum zmírnění | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM.Spectre | VC ++ 2017 verze 15.7 v14.14 knihovny pro spektrum (ARM) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM64.Spectre | VC ++ 2017 verze 15.7 v14.14 knihovny pro spektrum (ARM64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.x86.x64.Spectre | VC ++ 2017 verze 15.7 v14.14 knihovny pro spektrum (x86 a x64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Tools.14.11 | Sada nástrojů v14.11 verzi 15.4 2017 VC ++ | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | Sada nástrojů v14.12 verze 15,5 2017 VC ++ | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.13 | Sada nástrojů v14.13 VC ++ 2017 verze 15,6 operací | 15.0.27625.0

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
