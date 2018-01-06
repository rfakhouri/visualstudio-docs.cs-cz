---
title: IDebugDisassemblyStream2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDisassemblyStream2
helpviewer_keywords: IDebugDisassemblyStream2 interface
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 63426abcc059da3278569f433907d9f073e510b3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdisassemblystream2"></a>IDebugDisassemblyStream2
Toto rozhraní představuje proud pokyny.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDisassemblyStream2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění implementuje toto rozhraní pro podporu zpětný překlad kódu programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) metoda vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugDisassemblyStream2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Pro čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|Přečte pokyny od aktuální pozici v datovém proudu zpětný překlad.|  
|[Hledat](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|Přesune čtení ukazatele v datovém proudu zpětný překlad zadaný počet pokyny relativně k zadané pozici.|  
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|Vrátí identifikátor umístění kódu pro konkrétní kód kontext.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|Vrátí objekt kontextu kód odpovídající identifikátor zadaný kód umístění.|  
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|Vrátí identifikátor umístění kód, který představuje aktuální umístění v kódu.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|Získá zdrojový dokument spojené s tímto datovým proudem zpětný překlad.|  
|[Getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|Získá obor Tento datový proud zpětný překlad.|  
|[Getsize –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|Získá velikost tento datový proud zpětný překlad.|  
  
## <a name="remarks"></a>Poznámky  
 Datový proud zpětný překlad lze vytvořit k reprezentaci celého adresního prostoru nebo pouze funkce nebo modul v prostoru. Každý instrukce je reprezentována [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktura vrácený volání [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)