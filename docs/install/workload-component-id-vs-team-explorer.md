---
title: ID pracovního vytížení a komponenta Visual Studio Team Explorer 2017
titleSuffix: ''
description: Pomocí ID pracovního vytížení a komponenta Visual Studio poskytuje integrované testovací nástroje pro všeobecně testery
keywords: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 11/13/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.assetid: c6ef9a3b-d13d-49b4-9faa-51fa06b21e1f
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: f5b9d6b449a2f551e96132e07c0997455388fa82
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841504"
---
# <a name="visual-studio-team-explorer-2017-component-directory"></a>Visual Studio Team Explorer 2017 součástí adresáře

Tabulky v tomto seznamu stránce ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat jako závislost v manifestu VSIX. Všimněte si, že přidáme další součásti vydaných aktualizací sady Visual Studio.

Všimněte si také následující stránka:

* Každá úloha má vlastní oddíl, za nímž následuje Identifikátor pracovního vytížení a tabulku komponent, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **vyžaduje** součásti nainstaluje, když jste si nainstalovali úlohu.
* Pokud budete chtít, můžete nainstalovat také **doporučená** a **volitelné** komponenty.
* Přidali jsme také oddíl, který obsahuje další součásti, které nejsou pod něj nespadá u jakékoli úlohy.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. Určení závislostí naše minimální součástí pomocí tabulek na této stránce. V některých případech to může znamenat, že zadáváte pouze jednu komponentu z pracovního vytížení. V jiných scénářích může znamenat, že zadáte více komponent z jedné úlohy nebo více komponent z více úloh. Další informace najdete v tématu [jak: Migrace projektů rozšíření do sady Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak pomocí těchto identifikátorů najdete v části [pomocí parametrů příkazového řádku instalace sady Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam pracovního vytížení a komponenta ID pro ostatní produkty, naleznete v tématu [funkcí sady Visual Studio 2017 a ID součástí](workload-and-component-ids.md) stránky.

## <a name="visual-studio-core-editor-included-with-visual-studio-team-explorer-2017"></a>Základní editor Visual Studio (je součástí sady Visual Studio Team Explorer 2017)

**ID:** Microsoft.VisualStudio.Workload.CoreEditor

**Popis:** Visual Studio základní možnosti a prostředí, včetně úprav, správy zdrojového kódu podle syntaxe kódu a správy pracovních položek.

### <a name="components-included-by-this-workload"></a>Pomocí této úlohy zahrnuté komponenty

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Základním editoru sady Visual Studio | 15.8.27729.1 | Požadováno
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | Visual Studio úvodní stránka pro uživatele jazyka C++ | 15.0.27128.1 | volitelná,

## <a name="unaffiliated-components"></a>Nespojená komponenty

Toto jsou komponenty, které nejsou zahrnuty u jakékoli úlohy, ale může vybrat jako jednotlivých komponent.

ID součásti | Název | Version
--- | --- | ---
není k dispozici | není k dispozici | není k dispozici

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
* [Příručka pro správce aplikace Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
* [Vytvoření offline instalace sady Visual Studio](create-an-offline-installation-of-visual-studio.md)
