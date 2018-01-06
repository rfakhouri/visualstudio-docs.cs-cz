---
title: "Funkce háku sestavy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
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
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 958c33c623830af509185b3d35ef8a8b5956aaae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="report-hook-functions"></a>Sestava funkcí háku
Funkce háku sestavy, nainstalovat pomocí [_crtsetreporthook –](/cpp/c-runtime-library/reference/crtsetreporthook), se nazývá pokaždé, když [_crtdbgreport –](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) generuje sestavy ladění. Můžete použít, mimo jiné pro filtrování sestavy a zaměřit se na konkrétní typy přidělení. Funkce háku sestavy musí mít prototyp takto:  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Ukazatele, který můžete předat **_crtsetreporthook –** je typu **_crt_report_hook –**, jak jsou definovány v CRTDBG. V:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Při volání funkce háku, běhové knihovny *nRptType* argument obsahuje kategorii sestavy (**_CRT_WARN**, **_CRT_ERROR**, nebo **_CRT _ASSERT**), *szMsg* obsahuje ukazatel na řetězec zprávy plně sestavený sestavy a *retVal* Určuje, zda `_CrtDbgReport` by měly pokračovat normální spuštění Po generování sestavy nebo spuštění ladicího programu. (A *retVal* hodnota nula pokračuje v provádění, hodnotu 1 spustí ladicí program.)  
  
 Pokud hák má na starosti dotyčném zpráva úplně, tak, aby další vykazování se nevyžaduje, by měla vrátit **TRUE**. Vrátí-li **FALSE**, `_CrtDbgReport` bude sestava zpráva normálně.  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)