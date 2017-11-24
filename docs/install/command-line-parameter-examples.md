---
title: "Příklady parametr příkazového řádku pro instalaci sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 05/06/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: timsneath
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 44d16c4ebd713c0445743feac66b0026e520dd66
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Příklady parametr příkazového řádku pro instalaci Visual Studio 2017
Pro ilustraci postup [používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md), zde je několik příkladů, které můžete přizpůsobit tak, aby odpovídaly vašim potřebám.

V obou příkladech `vs_enterprise.exe`, `vs_professional.exe` a `vs_community.exe` představují odpovídající edice zaváděcího nástroje Visual Studio, což je soubor malá (přibližně 1 MB), který zahájí proces stahování. Pokud používáte jinou edici, nahraďte název příslušné zaváděcího nástroje.

> [!NOTE]
> Všechny příkazy vyžadují zvýšení oprávnění pro správu a řízení uživatelských účtů, výzva se zobrazí, pokud proces neběží řádku se zvýšenými oprávněními.

> [!NOTE]
>  Můžete použít `^` znak na konci příkazového řádku k řetězení více řádků do jednoho příkazu. Alternativně můžete jednoduše umístit tyto řádky společně na jednom řádku. V prostředí PowerShell, je ekvivalentem backtick (`` ` ``) znaků.

* Nainstalujte minimální instanci sady Visual Studio, s žádný interaktivní výzvy, ale zobrazí průběh:
```
vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
```

* Instalaci bezobslužně, plochy instance sady Visual Studio s Francouzská jazyková sada, vrácení jenom v případě, že je nainstalovaný produkt.
```
vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
```

> [!NOTE]
>  `--wait` Parametr je určen k použití v dávkovém souboru. V dávkovém souboru provádění dalšího příkazu nebude pokračovat až po dokončení instalace. `%ERRORLEVEL%` Proměnné prostředí bude obsahovat vrácenou hodnotu příkazu, jak je uvedeno v [používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md) stránky.

* Stáhněte si základní editoru Visual Studio (většina minimální konfigurace sady Visual Studio). Zahrnout pouze anglické jazykové sady:

```cmd
vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
```

* Stáhněte .NET plochy a .NET webové úlohy spolu se všechny doporučené součásti a rozšíření Githubu. Zahrnout pouze anglické jazykové sady:
```
vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
```

* Spusťte interaktivní instalaci všech úloh a součásti, které jsou k dispozici v edici Visual Studio 2017 Enterprise:
```
vs_enterprise.exe --all --includeRecommended --includeOptional
```

* Instalaci druhé, s názvem instance Visual Studio 2017 Professional na počítači s již nainstalován ve – podpora vývoje Node.js pro edice Visual Studio 2017 Community:
```
vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
```

* Odeberte komponentu nástrojích pro profilaci z výchozí nainstalována instance Visual Studio:
```
vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
```

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také

 * [Příručka administrátora sady Visual Studio](visual-studio-administrator-guide.md)
 * [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
 * [Vytvoření offline instalace Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
