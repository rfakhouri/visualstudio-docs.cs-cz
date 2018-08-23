---
title: 'Postupy: určení dalších informací o kódu pomocí __analysis_assume | Dokumentace Microsoftu'
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
- __analysis_assume
helpviewer_keywords:
- __analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
caps.latest.revision: 12
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a08ca5a35d08f284062323f2e75648852debb7bf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666418"
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>Postupy: Určení dalších informací o kódu pomocí __analysis_assume
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: určení dalších informací o kódu pomocí __analysis_assume](https://docs.microsoft.com/visualstudio/code-quality/how-to-specify-additional-code-information-by-using-analysis-assume).  
  
Můžete zadat informace pro nástroj pro analýzu kódu pro kód C/C++, který pomůže proces analýzy a snížit upozornění. Na další informace, použijte následující funkce:  
  
 `__analysis_assume(`  `expr`  `)`  
  
 `expr` -libovolný výraz, který předpokládá, že je vyhodnocen na hodnotu true.  
  
 Nástroj pro analýzu kódu předpokládá, že je reprezentována výrazem podmínka pravdivá v místě, kde funkce se zobrazí a bude platit pořád, dokud je změněn výrazu, například v přiřazením do proměnné.  
  
> [!NOTE]
>  `__analysis_assume` nemá žádný vliv optimalizace kódu. Mimo nástroj pro analýzu kódu `__analysis_assume` je definován jako no-op.  
  
## <a name="example"></a>Příklad  
 Následující kód používá `__analysis_assume` Chcete-li opravit toto upozornění analýzy kódu [C6388](../code-quality/c6388.md):  
  
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
  __analysis_assume(pc == NULL);   
  f(pc);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [__assume](http://msdn.microsoft.com/library/d8565123-b132-44b1-8235-5a8c8bff85a7)



