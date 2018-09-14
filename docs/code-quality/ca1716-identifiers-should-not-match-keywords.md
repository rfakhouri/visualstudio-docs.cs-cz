---
title: 'CA1716: Identifikátory by neměly odpovídat klíčovým slovům'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b5ee844da2c04a1dd6eac6a7ca458957dd22a71
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550606"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům
|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název oboru názvů, typ nebo člen viritual nebo rozhraní odpovídá vyhrazenému klíčovému slovu programovacího jazyka.

## <a name="rule-description"></a>Popis pravidla
 Identifikátory pro obory názvů, typy a virtuální a interface členy by neměly odpovídat klíčová slova, která jsou definována jazyky cílenými na modul common language runtime. V závislosti na jazyk, ve kterém se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovnu obtížně použitelnou.

 Toto pravidlo zkontroluje proti klíčových slov v těchto jazycích:

- Visual Basic

- C#

- C++/CLI

 Porovnávání se používá pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] klíčová slova a porovnání velká a malá písmena se používá pro jiné jazyky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název, který se nezobrazí v seznamu klíčových slov.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud jste se přesvědčili, že identifikátor nesmí být pro uživatele matoucí rozhraní API a je použitelné ve všech jazycích k dispozici v knihovně můžete potlačit upozornění tohoto pravidla [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].