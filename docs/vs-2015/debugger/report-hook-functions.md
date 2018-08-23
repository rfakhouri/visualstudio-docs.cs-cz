---
title: Funkce háku sestavy | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b9a87a9efe91c8a3739b88a39fac5c391218833
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670746"
---
# <a name="report-hook-functions"></a>Sestava funkcí háku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [funkce háku sestavy](https://docs.microsoft.com/visualstudio/debugger/report-hook-functions).  
  
Funkce háku sestavy, nainstalovat pomocí [_CrtSetReportHook](http://msdn.microsoft.com/library/1ae7c64f-8c84-4797-9574-b59f00f7a509), je volána pokaždé, když [_CrtDbgReport](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc) generuje sestavu ladění. Můžete použít, mimo jiné pro filtrování sestav a zaměřte se na konkrétní typy přidělení. Funkce háku sestavy by měl mít prototyp vypadat asi takto:  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Ukazatel, který můžete předat **_CrtSetReportHook** je typu **_crt_report_hook –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Při volání funkce háku, knihovny run-time *nRptType* argument obsahuje kategorie sestavy (**_CRT_WARN**, **_CRT_ERROR**, nebo **_CRT _ASSERT**), *szMsg* obsahuje ukazatel na řetězec zprávy sestaveném sestavy a *retVal* Určuje, zda `_CrtDbgReport` by měla pokračovat normální spuštění Po vygenerování sestavy nebo spuštění ladicího programu. (A *retVal* nulová hodnota pokračuje v provádění kódu, spustí ladicí program hodnotu 1.)  
  
 Pokud volání má na starosti dotyčný zpráva úplně, tak, aby další vykazování se nevyžaduje, měla by vrátit **TRUE**. Vrátí-li **FALSE**, `_CrtDbgReport` bude sestava zprávy normálně.  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



