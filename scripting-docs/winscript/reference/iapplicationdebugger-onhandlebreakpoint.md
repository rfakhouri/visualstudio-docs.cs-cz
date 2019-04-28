---
title: IApplicationDebugger::onHandleBreakPoint | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.onHandleBreakPoint
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::onHandleBreakPoint
ms.assetid: 31adcecd-d6c1-4222-ab2c-32ec2fefb322
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: edf8816cd646596ce1f897dfd9d949790d52b7b1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991356"
---
# <a name="iapplicationdebuggeronhandlebreakpoint"></a>IApplicationDebugger::onHandleBreakPoint
Zpracovává událost zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT onHandleBreakPoint(  
   IRemoteDebugApplicationThread*  prpt,  
   BREAKREASON                     br,  
   IActiveScriptErrorDebug*        pError  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `prpt`  
 [in] Vlákno, kde došlo k zarážce.  
  
 `br`  
 [in] Důvod pro zarážku.  
  
 `pError`  
 [in] Informace o chybě modulu runtime, zadat, pokud hodnota `br` je BREAKREASON_ERROR.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána při dosažení zarážky a `IDebugApplication::HandleBreakPoint` je volána.  
  
 Aplikace budou pozastaveny, dokud ladicí program integrovaného vývojového prostředí volá `IRemoteDebugApplication::ResumeFromBreakPoint`.  
  
## <a name="see-also"></a>Viz také  
 [Iapplicationdebugger – rozhraní](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::HandleBreakPoint](../../winscript/reference/idebugapplication-handlebreakpoint.md)   
 [IRemoteDebugApplication::ResumeFromBreakPoint](../../winscript/reference/iremotedebugapplication-resumefrombreakpoint.md)   
 [BREAKREASON – výčet](../../winscript/reference/breakreason-enumeration.md)