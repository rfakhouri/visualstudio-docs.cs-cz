---
title: Verze Visual Studia podporované pro Visualization &amp; Modeling SDK
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4ec6528176b02684a4235be29f4387da26193810
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="supported-visual-studio-editions-for-visualization-amp-modeling-sdk"></a>Verze Visual Studia podporované pro Visualization &amp; Modeling SDK
Seznam edice sady Visual Studio, které jsou podporovány jsou následující [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] v prostředí pro tvorbu a nasazení. Další informace o těchto edicích naleznete v tématu Microsoft [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [středisku pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=75628).

## <a name="authoring-edition"></a>Authoring Edition
 Pokud chcete definovat DSL, je třeba nainstalovat následující součásti:

|||
|-|-|
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio vizualizace a modelování SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>Edice nasazení
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] pro nasazení specifické pro doménu jazyky, které vytvoříte podporuje následující konfigurace:

-   Visual Studio Enterprise

-   Visual Studio Professional

-   Visual Studio Shell (integrovaný režim) redistributable package redistribuovatelný balíček

-   Visual Studio Shell (izolovaný režim) redistributable package redistribuovatelný balíček

> [!NOTE]
>  Chcete-li DSL ke spuštění v prostředí produktu, musíte nastavit **podporována edice VS** pole v Manifest rozšíření. Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).

## <a name="see-also"></a>Viz také

- [Glosář nástroje jazyka domény](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
