---
title: Visual Studio plochy Express 2017 pracovního vytížení a součást ID
description: Pomocí úloh a ID součástí k instalaci sady Visual Studio pomocí příkazového řádku nebo zadejte v závislosti na manifestu VSIX
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
ms.assetid: a3c0cc76-e3ce-435c-a1af-a6318b5a4dbe
ms.workload:
- multiple
ms.openlocfilehash: fe83e09316493ba68b67e3ccc0c785b7093032dd
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281768"
---
# <a name="visual-studio-2017-desktop-express-component-directory"></a>Visual Studio Express plochy 2017 součástí adresáře

Tabulky v tomto seznamu stránky ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat v závislosti na manifestu VSIX. Všimněte si, že přidáme další součásti, jako jsme vydání aktualizace pro Visual Studio.

Všimněte si také následující stránka:

* Každé zatížení má vlastní části, a potom podle ID úlohy a tabulku součásti, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **požadované** součásti se nainstalují při instalaci zatížení.
* Pokud zvolíte možnost, můžete taky nainstalovat **doporučeno** a **volitelné** součásti.
* Přidali jsme také oddíl, který uvádí další součásti, které nejsou spojit s jakoukoli úlohu.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. K určení závislostí naše minimální součástí použijte tabulky na této stránce. V některých případech to může znamenat, že zadáváte pouze jedna součást z pracovního vytížení. V jiných scénářích může znamenat, že zadáváte více součástí z jediné úlohy nebo více součástí z více úloh. Další informace najdete v tématu [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak používat tyto identifikátory najdete v tématu [pomocí parametrů příkazového řádku pro instalaci Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam úloh a ID součástí pro ostatní produkty, naleznete v části [zatížení 2017 Visual Studio a ID součástí](workload-and-component-ids.md) stránky.

## <a name="express-for-windows-desktop"></a>Express for Windows Desktop

**ID:** Microsoft.VisualStudio.Workload.WDExpress

**Popis:** vytvářet nativní a spravované aplikace jako WPF, WinForms a Win32 s deklaracemi syntaxe kódu úpravy zdrojového kódu a pracovní položky správy. Zahrnuje podporu pro C#, Visual Basic a Visual C++.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.Component.ClickOnce | Publikování ClickOnce | 15.7.27520.0 | Požadováno
Microsoft.Component.HelpViewer | Prohlížeč nápovědy | 15.6.27323.2 | Požadováno
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Požadováno
Microsoft.Component.VC.Runtime.OSSupport | Visual C++ runtime pro UPW | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.5.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.1 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.5.2.TargetingPack | Cílovou sadu rozhraní .NET framework 4.5.2 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.5.TargetingPack | Cílení na pack rozhraní .NET framework 4.5 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.SDK | Rozhraní .NET framework 4.6.1 SDK | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.1.TargetingPack | Cílovou sadu rozhraní .NET framework 4.6.1 | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.6.TargetingPack | Cílení na pack rozhraní .NET framework 4.6. | 15.6.27406.0 | Požadováno
Microsoft.Net.Component.4.TargetingPack | Cílení na pack rozhraní .NET framework 4 | 15.6.27406.0 | Požadováno
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Nástroje pro vývoj rozhraní .NET framework 4.6.1 | 15.7.27520.0 | Požadováno
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Nástroje pro vývoj rozhraní .NET framework 4 – 4.6 | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.Common.Azure.Tools | Nástroje pro připojení a publikování | 1.10.50912.1 | Požadováno
Microsoft.VisualStudio.Component.CoreEditor | Editor základní Visual Studio | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 nástrojů | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.NuGet | Správce balíčků NuGet | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.Compiler | Kompilátory jazyka C# a Visual Basic Roslyn | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# a Visual Basic | 15.0.27205.0 | Požadováno
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL runtime | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.SQL.CLR | Datové typy CLR systému SQL Server | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.SQL.CMDUtils | Nástroje příkazového řádku systému SQL Server | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.SQL.DataSources | Zdroje dat pro podporu systému SQL Server | 15.0.26621.2 | Požadováno
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Požadováno
Microsoft.VisualStudio.Component.SQL.NCLI | Nativní klient SQL serveru | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.7.27625.0 | Požadováno
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statické analytické nástroje | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.TextTemplating | Transformace textové šablony | 15.0.26208.0 | Požadováno
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI podpory | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Tools.ARM | Kompilátory jazyka Visual C++ a knihovny pro ARM | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | Kompilátory jazyka Visual C++ a knihovny pro ARM64 | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.VisualStudioData | Zdroje dat a odkazy na službu | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | Požadováno
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.7.27703.1 | Požadováno

## <a name="unaffiliated-components"></a>Nezávislou na komponenty

Toto jsou součásti, které nejsou součástí žádné úlohy, ale může být vybraný jako jednotlivé součásti.

ID součásti | Název | Version
--- | --- | ---
není k dispozici | není k dispozici | není k dispozici

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
