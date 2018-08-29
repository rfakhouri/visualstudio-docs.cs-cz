---
title: Příklady parametrů příkazového řádku pro instalaci sady Visual Studio
description: Přizpůsobení těchto příkladech, chcete-li vytvořit vlastní instalaci sady Visual Studio z příkazového řádku.
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f5e0b81f1d21348a11ceff8d74d326b95e311303
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138003"
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Příklady parametrů příkazového řádku pro instalaci sady Visual Studio 2017

Pro ilustraci jak [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md), tady je několik příkladů, které můžete přizpůsobit tak, aby odpovídala vašim potřebám.

V obou příkladech `vs_enterprise.exe`, `vs_professional.exe` a `vs_community.exe` představují příslušné verzi zaváděcí nástroj Visual Studio, což je soubor malé (přibližně 1 MB), který zahájí proces stahování. Pokud používáte jinou verzi, nahraďte název odpovídající zaváděcího nástroje.

> [!NOTE]
> Všechny příkazy vyžadovat zvýšení oprávnění pro správu a řízení uživatelských účtů, výzva se zobrazí, pokud proces není spuštěn řádku se zvýšenými oprávněními.
>
> [!NOTE]
>  Můžete použít `^` znak na konci příkazového řádku ke zřetězení více řádků do jediného příkazu. Alternativně můžete umístit společně na jediném řádku tyto řádky. V prostředí PowerShell, je ekvivalentní prvními (`` ` ``) znaků.

## <a name="using---installpath"></a>Pomocí--installPath

* Nainstalujte minimální instanci sady Visual Studio, s žádné interaktivní výzvy, ale zobrazuje průběh:

 ```cmd
 vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
 ```

* Aktualizace instance sady Visual Studio pomocí příkazového řádku se žádné interaktivní výzvy, ale zobrazuje průběh:

 ```cmd
 vs_enterprise.exe --update --quiet --wait
 vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
 ```

 > [!NOTE]
 > Oba příkazy jsou povinné. První příkaz aktualizuje instalační program sady Visual Studio. Druhý příkaz aktualizuje instanci sady Visual Studio. Aby se zabránilo dialogové okno Řízení uživatelských účtů, spusťte příkazový řádek jako správce.

* Klasické pracovní plochy instanci sady Visual Studio tichou instalaci, Francouzská jazyková sada, vrací pouze v případě, že je nainstalován produkt.

 ```cmd
 vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
 ```

 > [!NOTE]
 > `--wait` Parametr je určený pro použití v dávkovém souboru. V dávkovém souboru nebude pokračovat provádění dalšího příkazu až do dokončení instalace. `%ERRORLEVEL%` Proměnné prostředí bude obsahovat vrácenou hodnotu příkazu, jak je uvedeno v [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

## <a name="using---layout"></a>Pomocí parametru--rozložení

* Stáhněte si základní editor sady Visual Studio (nejvíce minimální konfigurace sady Visual Studio). Zahrnout pouze anglické jazykové sady:

 ```cmd
 vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
 ```

* Stáhněte .NET desktop a webové úlohy .NET spolu s všechny doporučené součásti a rozšíření GitHub. Zahrnout pouze anglické jazykové sady:

 ```cmd
 vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
 ```

## <a name="using---includerecommended"></a>Pomocí--includeRecommended

* Interaktivní instalací všechny úlohy a komponenty, které jsou k dispozici v edici Visual Studio 2017 Enterprise:

 ```cmd
 vs_enterprise.exe --all --includeRecommended --includeOptional
 ```

* Druhý, pojmenovanou instanci sady Visual Studio 2017 Professional můžete nainstalujte na počítač s Visual Studio 2017 Community edition už nainstalovaná s podporou pro vývoj v Node.js:

 ```cmd
 vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
 ```

## <a name="using---remove"></a>Pomocí parametru--odebrat

* Odebrat součást nástrojů pro profilaci z výchozího nainstalované instance sady Visual Studio:

 ```cmd
 vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
 ```

## <a name="using---path"></a>Pomocí parametru--cesty

Tyto parametry příkazového řádku jsou **nové ve verzi 15.7**. Další informace o nich najdete v tématu [použít parametry příkazového řádku instalace sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

* Pomocí instalace, mezipaměť a sdílené cesty:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache" --path shared="C:\VS\shared"`

* Pomocí jenom cesty instalace a mezipaměti:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache"`

* Pomocí instalace a sdílené cesty:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path shared="C:\VS\shared"`

* Použití pouze instalační cesta:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS"`

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Vytvoření offline instalace sady Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
