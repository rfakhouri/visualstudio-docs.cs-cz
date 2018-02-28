---
title: "Postupy: určení informací další kódu pomocí __analysis_assume | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __analysis_assume
helpviewer_keywords:
- __analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 72b72ce474a24d77b3b40513c2e69fb5ab4aea59
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>Postupy: Určení dalších informací o kódu pomocí __analysis_assume
Můžete zadat pomocné parametry nástroj pro analýzu kódu pro C/C++ kód, který bude pomůže procesu analýzy a snížit upozornění. Pokud chcete zadat další informace, použijte následující funkce:  
  
 `__analysis_assume(`  `expr`  `)`  
  
 `expr`-libovolný výraz, který se předpokládá, že vyhodnotit na hodnotu true.  
  
 Nástroj pro analýzu kódu předpokládá, že je hodnota true, v okamžiku, kdy funkce se zobrazí a zůstane hodnotu true, dokud je změnit výraz, například v podle přiřazení do proměnné, podmínky reprezentována výrazem.  
  
> [!NOTE]
>  `__analysis_assume`Optimalizace kódu neovlivní. Mimo nástroj pro analýzu kódu `__analysis_assume` je definován jako no-op.  
  
## <a name="example"></a>Příklad  
 Následující kód používá `__analysis_assume` opravit upozornění analýzy kódu [C6388](../code-quality/c6388.md):  
  
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
 [__assume](/cpp/intrinsics/assume)