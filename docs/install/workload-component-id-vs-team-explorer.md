---
title: Visual Studio Team Explorer 2017 pracovního vytížení a součást ID
description: Pomocí ID úlohy a součást Visual Studio pro zajištění integrované testovací nástroje Všestranní technici testerům, sada
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
ms.assetid: c6ef9a3b-d13d-49b4-9faa-51fa06b21e1f
ms.workload:
- multiple
ms.openlocfilehash: 36d83f4391e1ca726c1c4e6c299a26fcca72f9f2
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="visual-studio-team-explorer-2017-component-directory"></a>Visual Studio Team Explorer 2017 součástí adresáře

Tabulky v tomto seznamu stránky ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat v závislosti na manifestu VSIX. Všimněte si, že přidáme další součásti, jako jsme vydání aktualizace pro Visual Studio.

Všimněte si také následující stránka:

* Každé zatížení má vlastní části, a potom podle ID úlohy a tabulku součásti, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **požadované** součásti se nainstalují při instalaci zatížení.
* Pokud zvolíte možnost, můžete taky nainstalovat **doporučeno** a **volitelné** součásti.
* Přidali jsme také oddíl, který uvádí další součásti, které nejsou spojit s jakoukoli úlohu.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. K určení závislostí naše minimální součástí použijte tabulky na této stránce. V některých případech to může znamenat, že zadáváte pouze jedna součást z pracovního vytížení. V jiných scénářích může znamenat, že zadáváte více součástí z jediné úlohy nebo více součástí z více úloh. Další informace najdete v tématu [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak používat tyto identifikátory najdete v tématu [pomocí parametrů příkazového řádku pro instalaci Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam úloh a ID součástí pro ostatní produkty, naleznete v části [zatížení 2017 Visual Studio a ID součástí](workload-and-component-ids.md) stránky.

## <a name="visual-studio-core-editor-included-with-visual-studio-team-explorer-2017"></a>Visual Studio základní editor (je součástí Visual Studio Team Explorer 2017)

**ID:** Microsoft.VisualStudio.Workload.CoreEditor

**Popis:** prostředí prostředí sady Visual Studio jádra, včetně syntaxe využívající kód úpravy, pro řízení zdrojového kódu a pracovní položky správy.

### <a name="components-included-by-this-workload"></a>Součásti zahrnuté tímto zatížením

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Editor základní Visual Studio | 15.6.27309.0 | Požadováno
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | Visual Studio úvodní stránka pro uživatele C++ | 15.0.27128.1 | Nepovinné

## <a name="unaffiliated-components"></a>Nezávislou na komponenty

Toto jsou součásti, které nejsou součástí žádné úlohy, ale může být vybraný jako jednotlivé součásti.

ID součásti | Název | Version
--- | --- | ---
není k dispozici | není k dispozici | není k dispozici

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
