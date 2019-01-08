---
title: Ijsdebugdatatarget – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: a9b784d6-958f-4d55-b3f6-c2d6b260a16b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e14046443ca0560deacb6ddb6e39b1fc25d18fea
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097419"
---
# <a name="ijsdebugdatatarget-interface"></a>IJsDebugDataTarget – rozhraní
Implementovaný ladicí program poskytuje funkce pro přístup a změnu stavu cílového procesu ladicího programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
IJsDebugDataTarget : public IUnknown;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[IJsDebugDataTarget::AllocateVirtualMemory – metoda](../../winscript/reference/ijsdebugdatatarget-allocatevirtualmemory-method.md)|Rezervuje a/nebo potvrdí změny v oblasti paměti v rámci virtuálního adresového prostoru cílového procesu.|  
|[IJsDebugDataTarget::CreateStackFrameEnumerator – metoda](../../winscript/reference/ijsdebugdatatarget-createstackframeenumerator-method.md)|Vytvoří čítač pro rámce zásobníku.|  
|[IJsDebugDataTarget::FreeVirtualMemory – metoda](../../winscript/reference/ijsdebugdatatarget-freevirtualmemory-method.md)|Uvolní a/nebo rozváže oblast paměti v rámci virtuálního adresového prostoru cílového procesu.|  
|[IJsDebugDataTarget::GetThreadContext – metoda](../../winscript/reference/ijsdebugdatatarget-getthreadcontext-method.md)|Načte kontext pro uvedená vlákna.|  
|[IJsDebugDataTarget::GetTlsValue – metoda](../../winscript/reference/ijsdebugdatatarget-gettlsvalue-method.md)|Pro vlákno, který se právě ladí načte hodnotu ve slotu vlákno místní úložiště (TLS) pro zadaný index TLS.|  
|[IJsDebugDataTarget::ReadBSTR – metoda](../../winscript/reference/ijsdebugdatatarget-readbstr-method.md)|Čtení BSTR z cíle ladění.|  
|[IJsDebugDataTarget::ReadMemory – metoda](../../winscript/reference/ijsdebugdatatarget-readmemory-method.md)|Čtení paměti cílového procesu.|  
|[IJsDebugDataTarget::ReadNullTerminatedString – metoda](../../winscript/reference/ijsdebugdatatarget-readnullterminatedstring-method.md)|Přečte zadaný počet znaků z cíle.|  
|[IJsDebugDataTarget::WriteMemory – metoda](../../winscript/reference/ijsdebugdatatarget-writememory-method.md)|Čtení paměti cílového procesu.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)