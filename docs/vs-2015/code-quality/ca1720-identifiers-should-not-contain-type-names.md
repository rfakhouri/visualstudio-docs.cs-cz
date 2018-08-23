---
title: 'CA1720: Identifikátory by neměly obsahovat názvy typů | Dokumentace Microsoftu'
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
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d3060590cd43106d1580669e9a91e76cdfc3437e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628660"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Identifikátory by neměly obsahovat názvy typů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1720: identifikátory by neměly obsahovat názvy typů](https://docs.microsoft.com/visualstudio/code-quality/ca1720-identifiers-should-not-contain-type-names).  
  
TypeName | IdentifiersShouldNotContainTypeNames |  
| ID kontroly | CA1720 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Název parametru v externě viditelném členu obsahuje název datového typu.  
  
 -nebo-  
  
 Název externě viditelného členu obsahuje název typu dat pro konkrétní jazyk.  
  
## <a name="rule-description"></a>Popis pravidla  
 Názvy parametrů a členů se lépe používají ke komunikaci jejich význam než se popisují jejich typ, který má být poskytuje nástroje pro vývoj. Pro názvy členů Pokud je třeba zadat název datového typu, použijte název nezávislým na jazyku místo jeden konkrétní jazyk. Například místo C# typu název "int", použijte název typu nezávislým na jazyku dat datový typ Int32.  
  
 Každý samostatný token název parametru nebo člen je porovnávána s následující názvy typů dat pro konkrétní jazyk, v podobě velká a malá písmena:  
  
-   BOOL  
  
-   WChar  
  
-   Int8  
  
-   UInt8  
  
-   krátké  
  
-   UShort  
  
-   int  
  
-   UInt  
  
-   Integer  
  
-   Uinteger –  
  
-   Long  
  
-   ULong  
  
-   bez znaménka  
  
-   podepsané  
  
-   plovoucí desetinnou čárkou  
  
-   float32  
  
-   float64  
  
 Kromě toho názvy parametru jsou zkontrolovány také proti následující názvy typů dat nezávislým na jazyku písmen:  
  
-   Objekt  
  
-   obj  
  
-   Boolean  
  
-   Char  
  
-   String  
  
-   SByte  
  
-   Byte  
  
-   UByte  
  
-   Int16  
  
-   UInt16  
  
-   Int32  
  
-   UInt32  
  
-   Int64  
  
-   UInt64  
  
-   IntPtr  
  
-   PTR  
  
-   Ukazatel  
  
-   UInptr  
  
-   UPtr  
  
-   UPointer  
  
-   Single  
  
-   Double  
  
-   Desetinné číslo  
  
-   identifikátor GUID  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 **Pokud je aktivována před parametr:**  
  
 Nahraďte datového typu identifikátoru názvu parametru termín, který lépe popisuje jeho význam nebo obecnějším pojmem, jako například 'value'.  
  
 **Pokud je aktivována před členem:**  
  
 Nahraďte konkrétní jazyk datového typu identifikátoru název člena termín, který lépe popisuje jeho význam, jazykově nezávislým ekvivalentem nebo obecnějším pojmem, jako například 'value'.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Příležitostné použití založené na typ parametru a člen názvů může být vhodné. Ale pro vývoj, žádné známé scénáře nastat, pokud by měla potlačit upozornění tohoto pravidla. Pro knihovny, které mají předchozí dodán budete muset potlačit upozornění tohoto pravidla.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1719: Názvy parametrů by neměly odpovídat názvům členů](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)



