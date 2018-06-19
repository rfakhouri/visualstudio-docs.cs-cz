---
title: Přehled Analýzy kódu pro C/C++
ms.date: 04/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: ea576ba794350e6cee6b20f8ef9adb62f82a9c51
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031563"
---
# <a name="code-analysis-for-cc-overview"></a>Analýza kódu pro C/C++ – přehled

Nástroje Analýza kódu C/C++ poskytuje informace o možných defekty ve zdrojovém kódu C/C++. Přetečení vyrovnávací paměti, neinicializovaného paměti zahrnout běžné kódování chyby oznámené službou nástroj, dereferences ukazatele null a nevracení paměti a prostředků. Nástroj můžete spustit také kontroly proti [C++ základní pokyny](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="ide-integrated-development-environment-integration"></a>Integrace rozhraní IDE (integrované vývojové prostředí)

Nástroj pro analýzu kódu jsou plně integrované v prostředí Visual Studio IDE.

Během procesu vytváření všechna upozornění vygenerované zdrojový kód zobrazí v seznamu chyb. Můžete přejít na zdrojový kód, který způsobil upozornění a můžete zobrazit další informace o příčině a možná řešení problému.

## <a name="command-line-support"></a>Podporu příkazového řádku

Také můžete nástroj pro analýzu z příkazového řádku, jak je znázorněno v následujícím příkladu:

```cmd
C:\>cl /analyze Sample.cpp
```

**Visual Studio 2017 verze 15.7 a novější** s žádné sestavení systému, včetně CMake můžete spustit nástroj z příkazového řádku.

## <a name="pragma-support"></a>Podpora #pragma

Můžete použít `#pragma` – direktiva považovat upozornění jako chyby; povolit nebo zakázat upozornění a potlačení upozornění pro jednotlivé řádky kódu. Další informace najdete v tématu [postupy: nastavení vlastností analýzy kódu pro projekty C/C++](how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="annotation-support"></a>Podpora – Poznámka

Poznámky zlepšit přesnost analýza kódu. Poznámky poskytují další informace o podmínkách před a po na funkce parametry a návratové typy. Další informace najdete v tématu [postup: Zadejte další informace kódu pomocí __analysis_assume](../code-quality/how-to-specify-additional-code-information-by-using-analysis-assume.md)

## <a name="run-analysis-tool-as-part-of-check-in-policy"></a>Spusťte nástroj pro analýzu v rámci zásad vrácení se změnami

Můžete chtít vyžadovat, aby všechny zdrojového kódu vrácení se změnami splňovat určité zásady. Zejména budete chtít Ujistěte se, zda analýza byla spuštěna jako krok pro poslední místní sestavení. Další informace o povolení zásady pro analýzu kódu vrácení se změnami, najdete v části [vytváření a používání vrácení se změnami zásad analýzy kódu](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

## <a name="team-build-integration"></a>Integrace sestavení Team

Chcete-li spustit nástroj pro analýzu kódu jako krok pro můžete použít integrované funkce systém sestavení [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] proces sestavení. Další informace najdete v tématu [sestavení a verze](/vsts/build-release/index).

## <a name="see-also"></a>Viz také

- [Rychlý úvod: Analýza kódu pro C/C++](quick-start-code-analysis-for-c-cpp.md)
- [Návod: Analýza kódu C/C++ na výskyt závad](walkthrough-analyzing-c-cpp-code-for-defects.md)
- [Upozornění Analýzy kódu pro C/C++](code-analysis-for-c-cpp-warnings.md)
- [Použití kontrolních mechanismů C++ Core Guidelines](using-the-cpp-core-guidelines-checkers.md)
- [C++ základní pokyny pro kontrolu odkaz](code-analysis-for-cpp-corecheck.md)
- [Určení pravidel C++, která se mají spustit, pomocí sad pravidel](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [Analýza kvality ovladačů pomocí nástrojů pro analýzu kódu](/windows-hardware/drivers/develop/analyzing-driver-quality-by-using-code-analysis-tools)
- [Ovladače upozornění analýzy kódu pro](/windows-hardware/drivers/devtest/prefast-for-drivers-warnings)
