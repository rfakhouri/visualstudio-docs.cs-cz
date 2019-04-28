---
title: 'Postupy: Určení dalších informací o kódu pomocí funkce _Analysis_assume'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 25ce2a97acd248e546fdfab1a1b5c3f22e085f0c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63403118"
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>Postupy: Určení dalších informací o kódu pomocí funkce _Analysis_assume
Můžete zadat informace pro nástroj pro analýzu kódu pro kód C/C++, který pomůže proces analýzy a snížit upozornění. Na další informace, použijte následující funkce:

 `_Analysis_assume(`  `expr`  `)`

 `expr` -libovolný výraz, který předpokládá, že je vyhodnocen na hodnotu true.

 Nástroj pro analýzu kódu předpokládá, že je reprezentována výrazem podmínka pravdivá v místě, kde funkce se zobrazí a bude platit pořád, dokud je změněn výrazu, například v přiřazením do proměnné.

> [!NOTE]
> `_Analysis_assume` nemá žádný vliv optimalizace kódu. Mimo nástroj pro analýzu kódu `_Analysis_assume` je definován jako no-op.

## <a name="example"></a>Příklad
 Následující kód používá `_Analysis_assume` Chcete-li opravit toto upozornění analýzy kódu [C6388](../code-quality/c6388.md):

```
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

// calls free and sets ch to null
void FreeAndNull(char* ch);

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

void test( )
{
  char *pc = (char*)malloc(5);
  FreeAndNull(pc);
  _Analysis_assume(pc == NULL);
  f(pc);
}
```

## <a name="see-also"></a>Viz také
 [__assume](/cpp/intrinsics/assume)