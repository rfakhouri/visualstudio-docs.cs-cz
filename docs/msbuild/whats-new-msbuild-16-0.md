---
title: Co&#39;nového v MSBuild 16.0 | Dokumentace Microsoftu
ms.date: 03/11/2019
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: '>=vs-2019'
ms.openlocfilehash: 9fb23c8a48493056c9a37f510cefea3cc3374095
ms.sourcegitcommit: 4c7a0c2d712eb24609216577a793e912a6083eaf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "57986958"
---
# <a name="whats-new-in-msbuild-160"></a>Co je nového v MSBuild 16.0

Tento článek popisuje vlastnosti v MSBuild 16.0 a aktualizované funkce. Pro prováděcí (pouze koncept) poznámky k verzi, přečtěte si téma [ MSBuild 16.0](https://gist.github.com/rainersigwald/009627466f03964d0028e16fda633d9c).

## <a name="changed-path"></a>Změněné cesta

 Nástroj MSBuild je nainstalována v *\Current* jednotlivými verzemi sady Visual Studio ve složce. Například *C:\Program Files (x86) \Microsoft Visual Studio\Current\Enterprise\MSBuild*. Následující modul Powershellu můžete použít také k vyhledání nástroje MSBuild: [vssetup.powershell](https://github.com/Microsoft/vssetup.powershell).

## <a name="changed-properties"></a>Změněné vlastnosti

 Byly aktualizovány následující vlastnosti nástroje MSBuild kvůli nové číslo verze.

- `MSBuildToolsVersion` pro tuto verzi sady nástrojů je "Current". Verze sestavení je stejný jako v sadě Visual Studio 2017, které 15.1.0.0.

- `VisualStudioVersion` pro tuto verzi sady nástrojů je "16,0"

## <a name="updates"></a>Aktualizace

MSBuild (a Visual Studio) nyní cílí na .NET Framework 4.7.2. Pokud chcete používat nové funkce rozhraní API nástroje MSBuild, musíte upgradovat také sestavení, ale stávající kód bude fungovat i nadále.

## <a name="see-also"></a>Viz také:
- [MSBuild](../msbuild/msbuild.md)
