---
title: Verze Visual Studia podporované pro Visualization and Modeling SDK
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1e5898a95f10875f0880e4b4799f17b78aa8e79b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60073329"
---
# <a name="supported-visual-studio-editions-for-visualization--modeling-sdk"></a>Verze Visual Studia podporované pro Visualization & Modeling SDK

Toto jsou seznamy edice sady Visual Studio, které jsou podporovány [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] v prostředí pro vytváření a nasazení. Další informace o těchto vydáních najdete v tématu Microsoft Visual Studio [středisko pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=75628).

## <a name="authoring-edition"></a>Vytváření Edition

Pokud chcete definovat DSL, musíte mít nainstalovaný následující komponenty:

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio Visualization and Modeling SDK|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>Edice nasazení

[!INCLUDE[dsl](../modeling/includes/dsl_md.md)] podporuje následující konfigurace pro jazyky specifické pro doménu, která bude sestavena nasazení:

- Visual Studio Enterprise

- Visual Studio Professional

- Visual Studio Shell (integrovaný režim) redistributable package Distribuovatelný balíček

- Visual Studio Shell (izolovaný režim) redistributable package Distribuovatelný balíček

> [!NOTE]
> Chcete-li DSL ke spuštění v prostředí produktu, je nutné nastavit **podporované edice VS** pole v manifestu rozšíření. Další informace najdete v tématu [nasazení řešení jazyka specifického pro doménu](../modeling/deploying-domain-specific-language-solutions.md).

## <a name="see-also"></a>Viz také:

- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)