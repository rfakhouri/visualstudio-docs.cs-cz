---
title: Co je nového v profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ca95259ad8f31822e235c470e437daf0adaadc3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53865476"
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového v nástrojích pro profilaci [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

Diagnostické nástroje zahrnují nové vizualizace, abyste mohli snadno identifikovat problémy ve vaší aplikaci vyžadující opravu. Diagnostické nástroje nyní zahrnují podporu pro aplikace ASP.NET.

Další informace najdete v tématu [poznámky k verzi pro [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](/visualstudio/releasenotes/vs2017-relnotes#debuggingdiag).

A **Souhrn** přidala karta nástroje, které vám umožní zaměřit se na klíčové oblasti pro analýzu výkonu. Tato karta ukazuje, kolik události došlo, umožňuje pořizovat snímky haldy a umožňuje rychle Povolit shromažďování dat o využití procesoru. Toto zobrazení uvádí některé [Application insights](https://azure.microsoft.com/en-us/documentation/articles/app-insights-visual-studio/) nebo [Analýza uživatelského prostředí](/visualstudio/releasenotes/vs2017-relnotes#UIAnalysis) události. Pro Visual Studio Enterprise, je navíc toto zobrazení také zobrazuje události IntelliTrace.

![Karta Souhrn nástroje Diagnostika](../profiling/media/DiagToolsSummaryTab-2.png "DiagToolsSummaryTab")

Nástroj využití procesoru je [nové vizualizace](../profiling/Beginners-Guide-to-Performance-Profiling.md) ke snadnější identifikaci funkce, které bývají nejčastějším způsobovat problémy s výkonem. Nové **volající/volaný** zobrazení umožňuje prozkoumat náklady na volání do a z vybrané funkce.

![Diagnostické nástroje volající/volaný zobrazení](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")

## <a name="see-also"></a>Viz také:

- [Profil v sadě Visual Studio](../profiling/index.md)
- [Nejdřív se podívejte na nástroje pro profilaci](../profiling/profiling-feature-tour.md)