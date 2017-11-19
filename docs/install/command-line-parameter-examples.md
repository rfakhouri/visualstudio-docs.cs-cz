---
title: "Příklady parametr příkazového řádku pro instalaci sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 05/06/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: timsneath
ms.author: tims
manager: ghogen
ms.openlocfilehash: a3b12bfe0c289bfdefc6e3107960fd94889df287
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
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
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také

 * [Příručka administrátora sady Visual Studio](visual-studio-administrator-guide.md)
 * [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
 * [Vytvoření offline instalace Visual Studio 2017](create-an-offline-installation-of-visual-studio.md)
