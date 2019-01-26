---
title: ID pracovního vytížení a komponenta Visual Studio Test Controller 2017
titleSuffix: ''
description: Rozdělení automatizovaných testů mezi více počítačů pomocí ID pracovního vytížení a komponenta Visual Studio
keywords: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 11/13/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.prod: visual-studio-dev15
ms.assetid: fbbda9c8-d2c6-474d-b52d-a95227d52fe7
ms.workload:
- multiple
ms.openlocfilehash: 173f92ea713dcbe88ba1a3434bbb09b6588f3dd0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54977975"
---
# <a name="visual-studio-test-controller-2017-component-directory"></a>Visual Studio Test Controller 2017 součástí adresáře

Tabulky v tomto seznamu stránce ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat jako závislost v manifestu VSIX. Všimněte si, že přidáme další součásti vydaných aktualizací sady Visual Studio.

Všimněte si také následující stránka:

* Každá úloha má vlastní oddíl, za nímž následuje Identifikátor pracovního vytížení a tabulku komponent, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **vyžaduje** součásti nainstaluje, když jste si nainstalovali úlohu.
* Pokud budete chtít, můžete nainstalovat také **doporučená** a **volitelné** komponenty.
* Přidali jsme také oddíl, který obsahuje další součásti, které nejsou pod něj nespadá u jakékoli úlohy.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. Určení závislostí naše minimální součástí pomocí tabulek na této stránce. V některých případech to může znamenat, že zadáváte pouze jednu komponentu z pracovního vytížení. V jiných scénářích může znamenat, že zadáte více komponent z jedné úlohy nebo více komponent z více úloh. Další informace najdete v tématu [jak: Migrace projektů rozšíření do sady Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak pomocí těchto identifikátorů najdete v části [pomocí parametrů příkazového řádku instalace sady Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam pracovního vytížení a komponenta ID pro ostatní produkty, naleznete v tématu [funkcí sady Visual Studio 2017 a ID součástí](workload-and-component-ids.md) stránky.

## <a name="test-controller"></a>Kontroler testů

**ID:** Microsoft.VisualStudio.Workload.TestController

**Popis:** Rozdělení automatizovaných testů mezi více počítačů

### <a name="components-included-by-this-workload"></a>Pomocí této úlohy zahrnuté komponenty

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.ComponentGroup.TestTools.TestController | Základní funkce Kontroleru testů | 15.6.27309.0 | Požadováno

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
