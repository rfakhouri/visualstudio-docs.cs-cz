---
title: IDebugCodeContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCodeContext2
helpviewer_keywords: IDebugCodeContext2 interface
ms.assetid: 3670439e-2171-405d-9d77-dedb0f1cba93
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 75403c0597b2285aa9117f3ffb51acd01c967f3d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcodecontext2"></a>IDebugCodeContext2
Toto rozhraní představuje počáteční pozici instrukce kódu. Pro většinu architektury Runtime v současné době kontext kódu můžete představit jako adresu v datovém proudu spuštění programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext2 : IDebugMemoryContext2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladění modul implementuje tohoto rozhraní se týkají instrukce kódu do polohy dokumentu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Metody pro mnoho rozhraní vrátit toto rozhraní, obvykle, [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md). Používá se také hojně s [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) rozhraní také informace o řešení zarážek.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)|Získá kontext dokumentu, která odpovídá kontext active kódu.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugcodecontext2-getlanguageinfo.md)|Získá jazyk informace pro tento kontext kódu.|  
  
## <a name="remarks"></a>Poznámky  
 Klíčovým rozdílem mezi `IDebugCodeContext2` rozhraní a [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) rozhraní je, že `IDebugCodeContext2` je vždy instrukce zarovnaný. To znamená, že `IDebugCodeContext2` vždy ukazovat na začátku instrukce, zatímco `IDebugMemoryContext2` může vést k jakékoli bajtů paměti v architektuře běhu. `IDebugCodeContext2`se zvýší podle pokynů, a nikoli velikost základní úložiště (obvykle bajtů).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)   
 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)   
 [Další](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)