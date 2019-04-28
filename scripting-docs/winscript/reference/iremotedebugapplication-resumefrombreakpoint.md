---
title: IRemoteDebugApplication::ResumeFromBreakPoint | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.ResumeFromBreakPoint
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::ResumeFromBreakPoint
ms.assetid: a613cc2b-1d69-4713-a235-64372c253b4a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5844381188cb03c99ab0a44ed9b9e0fdbab67e6e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944173"
---
# <a name="iremotedebugapplicationresumefrombreakpoint"></a>IRemoteDebugApplication::ResumeFromBreakPoint
Pokračuje v aplikaci, která je aktuálně v zarážku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ResumeFromBreakPoint(  
   IRemoteDebugApplicationThread*  prptFocus,  
   BREAKRESUMEACTION               bra,  
   ERRORRESUMEACTION               era  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `prptFocus`  
 [in] Pro krokování režimy, vlákna, který má být ovlivněn krokování režimu.  
  
 `bra`  
 [in] Akce, který se má provést při obnovení aplikace.  
  
 `era`  
 [in] Akce provedená v případě, že aplikace zastavila z důvodu chyby.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda pokračuje v aplikaci, která je aktuálně v zarážku.  
  
## <a name="see-also"></a>Viz také  
 [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)   
 [Breakresumeaction – výčet](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION – výčet](../../winscript/reference/errorresumeaction-enumeration.md)