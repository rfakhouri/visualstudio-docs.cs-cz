---
title: Makra pro vytváření sestav | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: d6c35a2487e2917f62e35d6e819f899ee2151ffd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="macros-for-reporting"></a>Makra pro vytváření sestav
Můžete použít **_rptn –**, a **_rptfn –** maker, definovaných v CRTDBG. H nahradit použití `printf` příkazy pro ladění. Tyto makra automaticky zmizí ve vaší verzi sestavení při **_DEBUG –** není definována, takže není nutné do nich uzavřete **#ifdef**s.  
  
|– Makro|Popis|  
|-----------|-----------------|  
|**_RPT0 –**, **_RPT1 –**, **_RPT2 –**, **_RPT3 –**, **_RPT4 –**|Výstupy řetězec zprávy a nuly do čtyř argumentů. Pro _rpt1 – prostřednictvím **_rpt4 –**, řetězec zprávy slouží jako řetězec printf stylu formátování pro argumenty.|  
|**_RPTF0 –**, **_RPTF1 –**, **, _RPTF2 –**, **_RPTF4 –**|Stejné jako **_rptn –**, ale tyto makra také výstupní soubor název a řádek číslo kde se nachází makro.|  
  
 Podívejte se na následující příklad:  
  
```  
#ifdef _DEBUG  
    if ( someVar > MAX_SOMEVAR )  
        printf( "OVERFLOW! In NameOfThisFunc( ),  
               someVar=%d, otherVar=%d.\n",  
               someVar, otherVar );  
#endif  
```  
  
 Tento kód výstupy hodnoty `someVar` a `otherVar` k **stdout**. Můžete použít následující volání `_RPTF2` ohlásí tyto stejné hodnoty a navíc v souboru název a číslo řádku:  
  
```  
if (someVar > MAX_SOMEVAR) _RPTF2(_CRT_WARN, "In NameOfThisFunc( ), someVar= %d, otherVar= %d\n", someVar, otherVar );  
```  
  
 Pokud zjistíte, že konkrétní aplikaci potřebuje, ladění, které neposkytuje makra dodávaná s běhové knihovny jazyka C, můžete napsat makra navržená tak, aby vyhovovaly vašim požadavkům. V jednom z vaše soubory hlaviček, například můžete uvést kód jako následující příkaz pro definování makra názvem **ALERT_IF2**:  
  
```  
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
  
 Jednoho volání **ALERT_IF2** může provádět všechny funkce **printf** kód na začátku tohoto tématu:  
  
```  
ALERT_IF2(someVar > MAX_SOMEVAR, "OVERFLOW! In NameOfThisFunc( ),   
someVar=%d, otherVar=%d.\n", someVar, otherVar );  
```  
  
 Protože vlastní makro lze snadno změnit na více nebo méně podávat informace o do jiné cíle (podle toho, co je pohodlnější), tento přístup může být zvláště užitečné, jako momentální požadavků na ladění.  
  
## <a name="see-also"></a>Viz také  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)