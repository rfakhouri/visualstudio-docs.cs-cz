---
title: 'CA2133: Delegáti musí mít vazbu k metodám s konzistentní transparentností | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7ed73973125216e8f6056de8f104d9cbce98334f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902511"
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Delegáti musejí být připojeni k metodám s konzistentní transparentností
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2133: Delegáti musí mít vazbu k metodám s konzistentní transparentností](https://docs.microsoft.com/visualstudio/code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency).

|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

> [!NOTE]
>  Toto upozornění se použije pouze na kód, který je spuštěn CoreCLR (verze CLR, který je specifický pro Silverlight webových aplikací).

## <a name="cause"></a>příčina
 Toto upozornění je vyvoláno na metodě, která vytvoří vazbu delegáta označeného atributem <xref:System.Security.SecurityCriticalAttribute> na metodu, která je transparentní nebo která je označena pomocí <xref:System.Security.SecuritySafeCriticalAttribute>. Upozornění je také vyvoláno na metodě, která vytvoří vazbu transparentního delegáta nebo bezpečně kritického delegáta na kritickou metodu.

## <a name="rule-description"></a>Popis pravidla
 Typy delegátů a metody, které jsou svázat musí mít konzistentní transparentnost. Transparentní a bezpečné a kritické pro delegáty může být svázán pouze jiným metodám bezpečný a kritický nebo transparentní. Podobně kritické delegátů mohou být svázán pouze kritické metody. Tato pravidla vazby Ujistěte se, že pouze kód, který může vyvolat metodu prostřednictvím delegáta může mít také vyvolat stejnou metodu přímo. Například pravidel vazby zabránit transparentní kód volání kritický kód přímo prostřednictvím transparentního delegáta.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto upozornění, změňte průhlednost delegáta nebo metody, která se váže tak, že jsou ekvivalentní transparentnost z nich.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2133.delegatesmustbindwithconsistenttransparency/cs/ca2133 - delegatesmustbindwithconsistenttransparency.cs#1)]



