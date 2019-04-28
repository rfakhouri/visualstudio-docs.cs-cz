---
title: Ijsdebugdatatarget::getthreadcontext – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.GetThreadContext
apilocation:
- jscript9diag.dll
ms.assetid: faf2a689-6c49-4a7d-b5a6-2b323e2257a7
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7904ef81eb900c6466069267101f30d89e362a1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62582830"
---
# <a name="ijsdebugdatatargetgetthreadcontext-method"></a>IJsDebugDataTarget::GetThreadContext – metoda
Načte kontext pro uvedená vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetThreadContext(  
   DWORD threadId,  
   ULONG32 contextFlags,  
   ULONG32 contextSize,  
   void *pContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `threadId`  
 [in] Vlákno spuštěné v cílovém procesu.  
  
 `contextFlags`  
 [in] Určuje příznaky kontextu. To je stejné jako pole ContextFlags kontextu (pro další informace viz soubor winnt.h, hledejte možnost CONTEXT_ALL).  
  
 `contextSize`  
 [in] Velikost vyrovnávací paměti určená parametrem pContext.  
  
 `pContext`  
 [out] Do vyrovnávací paměti určená parametrem pContext přijme strukturu KONTEXT specifickou pro platformu.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)