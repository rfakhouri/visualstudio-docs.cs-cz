---
title: Co je nového v Profilování v sadě Visual Studio 2017 | Dokumentace Microsoftu
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: 8fcd01198877ef06eb398ce99fe467deb923546c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59232467"
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového v nástrojích pro profilaci [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Diagnostické nástroje zahrnují nové vizualizace, abyste mohli snadno identifikovat problémy ve vaší aplikaci vyžadující opravu. Diagnostické nástroje nyní zahrnují podporu pro aplikace ASP.NET.

Další informace najdete v tématu [poznámky k verzi pro [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](/visualstudio/releasenotes/vs2017-relnotes).

A **Souhrn** přidala karta nástroje, které vám umožní zaměřit se na klíčové oblasti pro analýzu výkonu. Tato karta ukazuje, kolik události došlo, umožňuje pořizovat snímky haldy a umožňuje rychle Povolit shromažďování dat o využití procesoru. Toto zobrazení uvádí některé [Application insights](/azure/azure-monitor/app/visual-studio) nebo [Analýza uživatelského prostředí](/visualstudio/releasenotes/vs2017-relnotes) události. Pro Visual Studio Enterprise, je navíc toto zobrazení také zobrazuje události IntelliTrace.

![Karta Souhrn nástroje Diagnostika](../profiling/media/diag-tools-summary-tab-2.png "DiagToolsSummaryTab")

Nástroj využití procesoru je [nové vizualizace](../profiling/Beginners-Guide-to-Performance-Profiling.md) ke snadnější identifikaci funkce, které bývají nejčastějším způsobovat problémy s výkonem. Nové **volající/volaný** zobrazení umožňuje prozkoumat náklady na volání do a z vybrané funkce.

![Diagnostické nástroje volající/volaný zobrazení](../profiling/media/diag-tools-caller-callee-2.png "DiagToolsCallerCallee")

## <a name="see-also"></a>Viz také:

- [Profil v sadě Visual Studio](../profiling/index.md)
- [Nejdřív se podívejte na nástroje pro profilaci](../profiling/profiling-feature-tour.md)