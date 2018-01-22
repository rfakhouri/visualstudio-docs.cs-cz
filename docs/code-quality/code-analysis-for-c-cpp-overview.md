---
title: "Analýza kódu pro C/C++ – přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28a5e13c2c56c7ecdb65efdfc1bd0b3c6eb47bfc
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="code-analysis-for-cc-overview"></a>Přehled Analýzy kódu pro C/C++
Analýza kódu C/C++ nástroj poskytuje informace pro vývojáře o možný výskyt závad v jejich zdrojového kódu C/C++. Přetečení vyrovnávací paměti, zrušení inicializovaného paměti zahrnout běžné kódování chyby oznámené službou nástroj, dereferences ukazatele null a nevracení paměti a prostředků.  
  
## <a name="ide-integrated-development-environment-integration"></a>Integrace rozhraní IDE (integrované vývojové prostředí)  
 Chcete-li přirozené vývojáři použít nástroj pro analýzu, jsou plně integrované v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Během procesu vytváření všechna upozornění vygenerované zdrojový kód zobrazí v seznamu chyb. Můžete přejít na zdrojový kód, který způsobil upozornění a můžete zobrazit další informace o příčině a možná řešení problému.  
  
## <a name="pragma-support"></a>#pragma podpory  
 Vývojáři mohou použít `#pragma` – direktiva považovat upozornění jako chyby; povolit nebo zakázat upozornění a potlačení upozornění pro jednotlivé řádky kódu. Další informace najdete v tématu [postupy: nastavení vlastností analýzy kódu pro projekty C/C++ ](how-to-set-code-analysis-properties-for-c-cpp-projects.md).  
  
## <a name="annotation-support"></a>Podpora – Poznámka  
 Poznámky zlepšit přesnost analýza kódu. Poznámky poskytují další informace o podmínkách před a po na funkce parametry a návratové typy. Další informace najdete v tématu [postup: Zadejte další informace kódu pomocí __analysis_assume](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)  
  
## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>Spusťte nástroj pro analýzu v rámci zásad vrácení se změnami  
 Můžete chtít vyžadovat, aby všechny zdrojového kódu vrácení se změnami splňovat určité zásady. Zejména budete chtít Ujistěte se, zda analýza byla spuštěna jako krok pro poslední místní sestavení. Další informace o povolení zásady pro analýzu kódu vrácení se změnami, najdete v části [vytváření a používání vrácení se změnami zásad analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)  
  
## <a name="team-build-integration"></a>Integrace sestavení Team  
 Chcete-li spustit nástroj pro analýzu kódu jako krok pro můžete použít integrované funkce systém sestavení [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] proces sestavení. Další informace najdete v tématu [sestavení a verze](/vsts/build-release/index).  
  
## <a name="command-line-support"></a>Podpora příkazového řádku  
 Kromě plné integraci v rámci vývojového prostředí vývojáři použít také nástroj pro analýzu z příkazového řádku, jak je znázorněno v následujícím příkladu:  
  
 `C:\>cl /analyze Sample.cpp`