---
title: 'CA1716: Identifikátory by neměly odpovídat klíčovým slovům | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cb5e3fe219d6ed8d976cf4bf03b3411dd5855a5c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189771"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
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

-   Visual Basic

-   C#

-   C++/CLI

 Porovnávání se používá pro [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] klíčová slova a porovnání velká a malá písmena se používá pro jiné jazyky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název, který se nezobrazí v seznamu klíčových slov.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud jste se přesvědčili, že identifikátor nesmí být pro uživatele matoucí rozhraní API a je použitelné ve všech jazycích k dispozici v knihovně můžete potlačit upozornění tohoto pravidla [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].



