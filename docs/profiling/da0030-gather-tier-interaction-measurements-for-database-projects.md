---
title: "DA0030: Získat měření interakce vrstev pro databázové projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0030
- vs.performance.rules.DA0030
- vs.performance.30
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ccb733d483026e7490d447c139e57700568a5f13
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="da0030-gather-tier-interaction-measurements-for-database-projects"></a>DA0030: Získat Měření interakce vrstev pro databázové projekty
|||  
|-|-|  
|Id pravidla|DA0030|  
|Kategorie|Použití nástroje pro profilaci|  
|Metoda profilace|Vzorkování|  
|Zpráva|Shromažďování měření interakce pro víceúrovňových aplikací budou nápovědy jste porozuměli vzorcům využití databáze a klíčová data přistupovat ke zpoždění. Zkuste to znovu profilace aplikace s povolenou možností profilace interakce vrstvy.|  
|Typ pravidla|Informace o|  
  
## <a name="cause"></a>příčina  
 Volání <xref:System.Data> podstatnou část data profilování jsou metody a nebyly shromažďovaných dat interakce vrstev v profilaci spustit. Zvažte profilace znovu a přidání dat interakce vrstev.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo aktivuje vždy, když je aktivita významných funkcí, které jsou umístěny v oborech názvů System.Data, včetně <xref:System.Data.Linq> <xref:System.Data.Linq>.  
  
 Víceúrovňových aplikací pomocí vrstev služby pro jejich prezentační a datové vrstvy. Datová vrstva často je samostatný proces spuštěný systém pro správu databází, jako je Microsoft Sql Server. Datová vrstva můžou běžet i na samostatný počítač od ostatních aplikace. Vzorkování profily poskytují jen málo informací do funkce a služby spuštěné mimo proces, nebo vzdáleně.  
  
 Nástroje pro profilaci můžete shromáždit informace časování pro víceúrovňových aplikací, které komunikují s vrstvou dat Microsoft Sql Server pomocí asynchronní volání služby ADO.NET. Je potřeba explicitně povolit profilace interakce vrstvy. Není zapnutá ve výchozím nastavení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Toto pravidlo je pouze informativní a nemusejí být nutné opravné akce.  
  
 Informace o způsobu přidání dat interakce vrstev pro profilace data z prostředí Visual Studio IDE najdete v tématu [shromažďování dat interakce vrstev](../profiling/collecting-tier-interaction-data.md). Informace o způsobu přidání dat interakce vrstev z příkazového řádku najdete v tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).