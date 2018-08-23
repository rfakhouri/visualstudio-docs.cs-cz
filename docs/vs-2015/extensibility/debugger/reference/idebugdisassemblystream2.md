---
title: IDebugDisassemblyStream2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDisassemblyStream2
helpviewer_keywords:
- IDebugDisassemblyStream2 interface
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f72cea28e47bdd14681c1f843a2620a43162885
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676877"
---
# <a name="idebugdisassemblystream2"></a>IDebugDisassemblyStream2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugDisassemblyStream2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2).  
  
Toto rozhraní představuje datový proud instrukcí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDisassemblyStream2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj implementuje toto rozhraní pro podporu zpětného překladu kódu programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) metoda vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugDisassemblyStream2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Pro čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|Přečte pokyny od aktuální pozice v datovém proudu zpětný překlad.|  
|[Hledání](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|Přesune ukazatel čtení ve službě stream zpětný překlad daný počet instrukcí vzhledem k zadané pozici.|  
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|Vrátí identifikátor umístění kódu pro kontext kódu.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|Vrátí objekt kontextu kód odpovídající identifikátor umístění zadaného kódu.|  
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|Vrátí identifikátor umístění kódu, který představuje aktuální umístění v kódu.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|Získá zdrojový dokument přidružené k tento datový proud zpětný překlad.|  
|[Getscope –](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|Získá obor tohoto datového proudu zpětný překlad.|  
|[GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|Získá velikost tohoto datového proudu zpětný překlad.|  
  
## <a name="remarks"></a>Poznámky  
 K reprezentaci celého adresního prostoru nebo jen funkce nebo modulu v prostoru lze vytvořit datový proud zpětný překlad. Každou instrukci je reprezentována [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktura vrácený voláním [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)

