---
title: ID pracovního vytížení a komponenta Visual Studio Feedback Client
titleSuffix: ''
description: ID pracovního vytížení a komponenta Visual Studio můžete zaslat podrobnou zpětnou vazbu pro Azure DevOps Services nebo Team Foundation Server
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
ms.assetid: 7392a100-100c-458c-9394-828695109015
ms.prod: visual-studio-windows
ms.technology: vs-installation
monikerRange: vs-2017
ms.openlocfilehash: f23af12a79e1b04c193e85c6fa31ac225af68a6d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62960746"
---
# <a name="visual-studio-feedback-client-component-directory"></a>Visual Studio Feedback Client součástí adresáře

Tabulky v tomto seznamu stránce ID, můžete použít k instalaci sady Visual Studio pomocí příkazového řádku nebo je můžete zadat jako závislost v manifestu VSIX. Všimněte si, že přidáme další součásti vydaných aktualizací sady Visual Studio.

Všimněte si také následující stránka:

* Každá úloha má vlastní oddíl, za nímž následuje Identifikátor pracovního vytížení a tabulku komponent, které jsou k dispozici pro pracovní vytížení.
* Ve výchozím nastavení **vyžaduje** součásti nainstaluje, když jste si nainstalovali úlohu.
* Pokud budete chtít, můžete nainstalovat také **doporučená** a **volitelné** komponenty.
* Přidali jsme také oddíl, který obsahuje další součásti, které nejsou pod něj nespadá u jakékoli úlohy.

Když nastavíte závislosti v manifestu VSIX, je nutné zadat ID součástí pouze. Určení závislostí naše minimální součástí pomocí tabulek na této stránce. V některých případech to může znamenat, že zadáváte pouze jednu komponentu z pracovního vytížení. V jiných scénářích může znamenat, že zadáte více komponent z jedné úlohy nebo více komponent z více úloh. Další informace najdete v tématu [jak: Migrace projektů rozšíření do sady Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) stránky.

Další informace o tom, jak pomocí těchto identifikátorů najdete v části [pomocí parametrů příkazového řádku instalace sady Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) stránky. A seznam pracovního vytížení a komponenta ID pro ostatní produkty, naleznete v tématu [funkcí sady Visual Studio 2017 a ID součástí](workload-and-component-ids.md) stránky.

## <a name="feedback-client"></a>Feedback Client

**ID:** Microsoft.VisualStudio.Workload.FeedbackClient

**Popis:** Feedback client umožňuje účastníkům poskytovat bohatou zpětnou vazbu pro Azure DevOps Services nebo Team Foundation Server.

### <a name="components-included-by-this-workload"></a>Pomocí této úlohy zahrnuté komponenty

ID součásti | Název | Version | Typ závislosti
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Feedback Client | 15.6.27406.0 | Požadováno

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
