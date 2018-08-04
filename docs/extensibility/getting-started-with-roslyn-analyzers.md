---
title: Začínáme s analyzátory Roslyn | Dokumentace Microsoftu
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 12c1bba1d07ab695f265425d6aeae6806589dcd4
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497846"
---
# <a name="get-started-with-roslyn-analyzers"></a>Začínáme s analyzátory Roslyn

Pomocí analyzátorů kódu za provozu, na základě projektu v sadě Visual Studio dodávat autoři rozhraní API pro analýzu kódu specifického pro doménu jako součást své balíčky NuGet. Protože tyto analyzátory využívají platformu kompilátoru .NET (s dřívějším kódovým označením Roslyn), může vést k upozornění ve vašem kódu při psaní ještě předtím, než jste dokončili řádku (žádné další čeká se na vytváření kódu ke zjišťování problémů). Analyzátory můžou také zařízení surface to napravit automatické kód prostřednictvím žárovky řádku sady Visual Studio umožňuje vyčistit váš kód okamžitě.

## <a name="get-started"></a>Začínáme

[Úvod analyzátory Roslyn živého kódu a návody](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Přidejte kód opravy názorný postup: poskytují uživatelům opravy pro analyzátor problémů](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Úvod a návod, analyzátor reálného světa mluví](http://channel9.msdn.com/events/Build/2015/3-725)

[Analyzátor Roslyn reálného světa](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , můžete se také podívat jako [komunikovat](http://channel9.msdn.com/events/Build/2015/3-725)

[Několik příkladů na githubu, seskupených do tři druhy analyzátory](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Úvod a prohlídku několik analyzátory mluví](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>Viz také:

- [Přehled analyzátory Roslyn](../code-quality/roslyn-analyzers-overview.md)
- [Další dokumentace na webu github OSS](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Pravidla FxCop implementováno s analyzátory Roslyn na Githubu](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)