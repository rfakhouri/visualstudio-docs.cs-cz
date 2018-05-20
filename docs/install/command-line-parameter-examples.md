---
title: Příklady parametr příkazového řádku pro instalaci sady Visual Studio
description: Přizpůsobte tyto příklady vytvořit vlastní instalace z příkazového řádku sady Visual Studio.
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
ms.openlocfilehash: 8e011dfd56adeaa832a1925e20e246fb66ce7979
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Příklady parametr příkazového řádku pro instalaci Visual Studio 2017

Pro ilustraci postup [používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md), zde je několik příkladů, které můžete přizpůsobit tak, aby odpovídaly vašim potřebám.

V obou příkladech `vs_enterprise.exe`, `vs_professional.exe` a `vs_community.exe` představují odpovídající edice zaváděcího nástroje Visual Studio, což je soubor malá (přibližně 1 MB), který zahájí proces stahování. Pokud používáte jinou edici, nahraďte název příslušné zaváděcího nástroje.

> [!NOTE]
> Všechny příkazy vyžadují zvýšení oprávnění pro správu a řízení uživatelských účtů, výzva se zobrazí, pokud proces neběží řádku se zvýšenými oprávněními.
>
> [!NOTE]
>  Můžete použít `^` znak na konci příkazového řádku k řetězení více řádků do jednoho příkazu. Alternativně můžete jednoduše umístit tyto řádky společně na jednom řádku. V prostředí PowerShell, je ekvivalentem backtick (`` ` ``) znaků.

## <a name="using---installpath"></a>Pomocí – installPath

* Nainstalujte minimální instanci sady Visual Studio, s žádný interaktivní výzvy, ale zobrazí průběh:

 ```cmd
 vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
 ```

* Aktualizace instance Visual Studio pomocí příkazového řádku s žádný interaktivní výzvy, ale zobrazí průběh:

 ```cmd
 vs_enterprise.exe --update --quiet --wait
 vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
 ```

 > [!NOTE]
 > Oba příkazy jsou povinné. První příkaz aktualizuje instalační program Visual Studio. V druhém příkazu aktualizuje instanci sady Visual Studio. Abyste se vyhnuli dialogové okno Řízení uživatelských účtů, příkazový řádek spustíte jako správce.

* Instalaci bezobslužně, plochy instance sady Visual Studio s Francouzská jazyková sada, vrácení jenom v případě, že je nainstalovaný produkt.

 ```cmd
 vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
 ```

 > [!NOTE]
 > `--wait` Parametr je určen k použití v dávkovém souboru. V dávkovém souboru provádění dalšího příkazu nebude pokračovat až po dokončení instalace. `%ERRORLEVEL%` Proměnné prostředí bude obsahovat vrácenou hodnotu příkazu, jak je uvedeno v [používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

## <a name="using---layout"></a>Pomocí--rozložení

* Stáhněte si základní editoru Visual Studio (většina minimální konfigurace sady Visual Studio). Zahrnout pouze anglické jazykové sady:

 ```cmd
 vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
 ```

* Stáhněte .NET plochy a .NET webové úlohy spolu se všechny doporučené součásti a rozšíření Githubu. Zahrnout pouze anglické jazykové sady:

 ```cmd
 vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
 ```

## <a name="using---includerecommended"></a>Pomocí – includeRecommended

* Spusťte interaktivní instalaci všech úloh a součásti, které jsou k dispozici v edici Visual Studio 2017 Enterprise:

 ```cmd
 vs_enterprise.exe --all --includeRecommended --includeOptional
 ```

* Instalaci druhé, s názvem instance Visual Studio 2017 Professional na počítači s již nainstalován ve – podpora vývoje Node.js pro edice Visual Studio 2017 Community:

 ```cmd
 vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
 ```

## <a name="using---remove"></a>Pomocí – odebrat

* Odeberte komponentu nástrojích pro profilaci z výchozí nainstalována instance Visual Studio:

 ```cmd
 vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
 ```

## <a name="using---path"></a>Pomocí – cesty

Tyto parametry příkazového řádku jsou **nové v 15.7**. Další informace o nich najdete v tématu [používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

* Pomocí instalace, mezipaměti a sdílené cesty:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache" --path shared="C:\VS\shared"`

* Používání jenom cesty instalace a mezipaměti:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache"`

* Pomocí instalace a sdílené cesty:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path shared="C:\VS\shared"`

* Pomocí instalační cestu:

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS"`

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [Vytvoření offline instalace Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
