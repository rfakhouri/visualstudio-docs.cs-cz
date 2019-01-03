---
title: Makra pro vytváření sestav | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.macros
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- macros, CRT reporting macros
- macros, debugging with
- _RPTFn macro
- CRT, reporting macros
- debugging [CRT], reporting macros
- _RPTn macro
ms.assetid: f2085314-a3a8-4caf-a5a4-2af9ad5aad05
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8453f00dda843f6940c518b7ed3ea83c8c261476
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53989971"
---
# <a name="macros-for-reporting"></a>Makra pro vytváření sestav
Pro ladění, můžete použít **_RPTn** a **_RPTFn** makra, definovaná v CRTDBG. H, chcete-li nahradit použití `printf` příkazy. Není nutné je inclose **#ifdef**s, protože jejich automaticky zmizí ve svojí vydané verzi sestavení, když **_DEBUG** není definován.  
  
|– Makro|Popis|  
|-----------|-----------------|  
|**_RPT0**, **_RPT1**, **_RPT2**, **_RPT3**, **_RPT4**|Vrací řetězec zprávy a 0 až čtyři argumenty. Pro _RPT1 prostřednictvím **_RPT4**, řetězec zprávy slouží jako řetězec stylu printf formátování pro argumenty.|  
|**_RPTF0**, **_RPTF1**, **_RPTF2**, **_RPTF4**|Stejné jako **_RPTn**, ale tato makra také výstup souboru název a číslo řádku kde se nachází makra.|  
  
 Vezměte v úvahu v následujícím příkladu:  
  
```cpp
#ifdef _DEBUG  
    if ( someVar > MAX_SOMEVAR )  
        printf( "OVERFLOW! In NameOfThisFunc( ),  
               someVar=%d, otherVar=%d.\n",  
               someVar, otherVar );  
#endif  
```  
  
 Tento kód vracel hodnoty `someVar` a `otherVar` k **stdout**. Můžete použít následující volání do `_RPTF2` hlášení tyto hodnoty stejné a navíc souboru název a číslo řádku:  
  
```cpp
if (someVar > MAX_SOMEVAR) _RPTF2(_CRT_WARN, "In NameOfThisFunc( ), someVar= %d, otherVar= %d\n", someVar, otherVar );  
```  
  
Můžete zjistit, konkrétní aplikace potřebuje, ladění, které neposkytují součástí knihovny run-time C makra. Pro tyto případy můžete napsat makro navržené, aby vyhovovaly vašim požadavkům. Jedním ze souborů hlaviček, například můžete zahrnout kód jako následující definovat makro volá **ALERT_IF2**:  
  
```cpp
#ifndef _DEBUG                  /* For RELEASE builds */  
#define  ALERT_IF2(expr, msg, arg1, arg2)  do {} while (0)  
#else                           /* For DEBUG builds   */  
#define  ALERT_IF2(expr, msg, arg1, arg2) \  
    do { \  
        if ((expr) && \  
            (1 == _CrtDbgReport(_CRT_ERROR, \  
                __FILE__, __LINE__, msg, arg1, arg2))) \  
            _CrtDbgBreak( ); \  
    } while (0)  
#endif  
```  
  
 Volání **ALERT_IF2** může provádět všechny funkce **printf** kódu:  
  
```cpp
ALERT_IF2(someVar > MAX_SOMEVAR, "OVERFLOW! In NameOfThisFunc( ),   
someVar=%d, otherVar=%d.\n", someVar, otherVar );  
```  
  
 Můžete snadno změnit vlastní – makro oznámit víc nebo míň informací do různých cílů. Tento přístup je zvlášť užitečné, jak se vyvíjí vaše požadavky na ladění.  
  
## <a name="see-also"></a>Viz také  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)
