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
ms.openlocfilehash: 41db830fbf7dcbe97f44d64ffa9b9701ec658c1e
ms.sourcegitcommit: 3dd15e019cba7d35dbabc1aa3bf55842a59f5278
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2018
ms.locfileid: "46370585"
---
# <a name="get-started-with-roslyn-analyzers"></a>Začínáme s analyzátory Roslyn

Pomocí analyzátorů kódu za provozu, na základě projektu v sadě Visual Studio dodávat autoři rozhraní API pro analýzu kódu specifického pro doménu jako součást své balíčky NuGet. Protože tyto analyzátory využívají platformu kompilátoru .NET (s dřívějším kódovým označením Roslyn), může vést k upozornění ve vašem kódu při psaní ještě předtím, než jste dokončili řádku (žádné další čeká se na vytváření kódu ke zjišťování problémů). Analyzátory můžou také zařízení surface to napravit automatické kód prostřednictvím žárovky řádku sady Visual Studio umožňuje vyčistit váš kód okamžitě.

## <a name="get-started"></a>Začínáme

[Úvod analyzátory Roslyn živého kódu a návody](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Přidejte kód opravy názorný postup: poskytují uživatelům opravy pro analyzátor problémů](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Úvod a návod, analyzátor reálného světa mluví](https://channel9.msdn.com/events/Build/2015/3-725)

[Analyzátor Roslyn reálného světa](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , můžete se také podívat jako [komunikovat](https://channel9.msdn.com/events/Build/2015/3-725)

[Několik příkladů na githubu, seskupených do tři druhy analyzátory](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Úvod a prohlídku několik analyzátory mluví](https://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>Viz také:

- [Přehled analyzátory Roslyn](../code-quality/roslyn-analyzers-overview.md)
- [Další dokumentace na webu github OSS](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Pravidla FxCop implementováno s analyzátory Roslyn na Githubu](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)