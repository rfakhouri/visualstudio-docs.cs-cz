---
title: Začínáme s analyzátory Roslyn | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 104e3a30589f5892c1440266afd7917486d704ec
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546645"
---
# <a name="getting-started-with-roslyn-analyzers"></a>Začínáme s analyzátory Roslyn
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí analyzátorů kódu za provozu, na základě projektu v sadě Visual Studio dodávat autoři rozhraní API pro analýzu kódu specifického pro doménu jako součást své balíčky NuGet.  Protože tyto analyzátory využívají platformu kompilátoru .NET (s dřívějším kódovým označením Roslyn), může vést k upozornění ve vašem kódu při psaní ještě předtím, než jste dokončili řádku (žádné další čeká se na vytváření kódu ke zjišťování problémů).  Analyzátory můžou také to napravit automatické kód prostřednictvím žárovky řádku sady Visual Studio umožňuje vyčistit váš kód okamžitě zařízení surface

## <a name="getting-started"></a>Začínáme
[Analyzátory Roslyn živého kódu úvod a návody](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Přidání kódu řeší názorný postup: Zadejte uživatele opravy pro analyzátor problémů](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Úvod a návod Přednáška analyzátor reálného světa](http://channel9.msdn.com/events/Build/2015/3-725)

[Reálného světa Roslyn analyzátor](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , můžete se také podívat jako [komunikovat](http://channel9.msdn.com/events/Build/2015/3-725)

[Několik příkladů na Githubu, seskupených do tři druhy analyzátory](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Úvod a prohlídku několik analyzátory mluví](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="other-resources"></a>Další zdroje
[Další dokumentace na webu GitHub OSS](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)

[Pravidla FxCop implementováno s analyzátory Roslyn na Githubu](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)
