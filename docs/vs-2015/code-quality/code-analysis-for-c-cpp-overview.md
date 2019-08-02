---
title: Analýza kódu pro C-C++ přehled | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- annotations, code analysis
- build integration, code analysis
- C/C++ code analysis
- IDE, code analysis
- pragma directive, code analysis
- code analysis, C/C++
- code analysis tool
- command line, code analysis
- C++, code analysis
- check-in policies, code analysis
- '#pragma directives, code analysis'
- C, code analysis
ms.assetid: 81f0c9e8-f471-4de5-aac4-99db336a8809
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: jillfra
ms.openlocfilehash: 0a0e744e1eb41cf9da816f2214176b37bfe4c8bf
ms.sourcegitcommit: b56dc6fadc6c924beed36bb4c2ccc16cf6bcfa1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/02/2019
ms.locfileid: "68740235"
---
# <a name="code-analysis-for-cc-overview"></a>Přehled Analýzy kódu pro C/C++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nástroj C/C++ Code Analysis poskytuje vývojářům informace o možných chybách ve svém kódu C/C++ source. Běžné chyby kódování hlášené nástrojem zahrnují přetečení vyrovnávací paměti, neinicializovaná paměť, zpětné odkazy na ukazatel s hodnotou null a paměti a nevrácené prostředky.  
  
## <a name="ide-integrated-development-environment-integration"></a>Integrace integrovaného vývojového prostředí (IDE)  
 Aby vývojáři mohli používat nástroj pro analýzu, je plně integrovaná v rámci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrovaného vývojového prostředí (IDE). Během procesu sestavení se všechna upozornění vygenerovaná pro zdrojový kód zobrazí v Seznam chyb. Můžete přejít ke zdrojovému kódu, který způsobil upozornění, a můžete si Zobrazit další informace o příčině a možných řešeních problému.  
  
## <a name="pragma-support"></a>Podpora #pragma  
 Vývojáři mohou použít `#pragma` direktivu k ponechání upozornění jako chyb, zapnutí nebo vypnutí upozornění a potlačení upozornění pro jednotlivé řádky kódu. Další informace najdete v tématu [jak: Povolí a zakáže analýzu kódu pro konkrétní C/C++ upozornění](https://msdn.microsoft.com/910b8518-71f1-4b2e-b012-70647795642a).  
  
## <a name="annotation-support"></a>Podpora poznámek  
 Poznámky zlepšují přesnost analýzy kódu. Poznámky poskytují další informace o parametrech funkce a návratových typech pro podmínky a ujednání. Další informace najdete v tématu [jak: Zadání dalších informací o kódu pomocí __analysis_assume](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>Spustit nástroj pro analýzu jako součást zásady vracení se změnami  
 Možná budete chtít vyžadovat, aby všechna vrácení se změnami zdrojového kódu splňovala určité zásady. Konkrétně je potřeba zajistit, aby byla analýza spuštěna jako krok posledního místního sestavení. Další informace o povolení zásad vrácení se změnami analýzy kódu naleznete v tématu [vytváření a používání zásad vrácení se změnami analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>Integrace sestavení týmu  
 Pomocí integrovaných funkcí systému sestavení lze nástroj pro analýzu kódu spustit jako krok [!INCLUDE[esprtfs](../includes/esprtfs-md.md)] procesu sestavení. Další informace naleznete v tématu [sestavování aplikace](/azure/devops/pipelines/index).  
  
## <a name="command-line-support"></a>Podpora příkazového řádku  
 Kromě úplné integrace v rámci vývojového prostředí mohou vývojáři také použít nástroj pro analýzu z příkazového řádku, jak je znázorněno v následujícím příkladu:  
  
 `C:\>cl /analyze Sample.cpp`
