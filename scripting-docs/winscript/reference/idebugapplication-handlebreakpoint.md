---
title: IDebugApplication::HandleBreakPoint | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.HandleBreakPoint
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::HandleBreakPoint
ms.assetid: 97219bdf-a39a-4e69-81ac-4ca2afe77ce5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e3444e6eedde9576216552e41abb0e97aafa2d7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63412383"
---
# <a name="idebugapplicationhandlebreakpoint"></a>IDebugApplication::HandleBreakPoint
Způsobí, že chcete blokovat aktuální vlákno a odešle oznámení této zarážky v ladicím programu integrovaného vývojového prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT HandleBreakPoint(  
   BREAKREASON         br,  
   BREAKRESUMEACTION*  pbra  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `br`  
 [in] Důvod pro přerušení.  
  
 `pbra`  
 [out] Akce se má provést, když ladicí program pokračuje v aplikaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Modul jazyka volá tuto metodu v kontextu vlákna, které narazí na zarážku. Tato metoda blokuje aktuální vlákno a odešle oznámení zarážku v ladicím programu integrovaného vývojového prostředí. Když ladicí program pokračuje v aplikaci, `pbra` parametr určuje, jaká akce se má provést.  
  
> [!NOTE]
> Modul jazyka může být volána vláknem provádění úkolů, například jako zobrazení výčtu zásobník snímků nebo vyhodnocení výrazů během zarážku.  
  
 Tato metoda způsobí, že `IApplicationDebugger::onHandleBreakPoint` volat.  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onHandleBreakPoint](../../winscript/reference/iapplicationdebugger-onhandlebreakpoint.md)   
 [Breakreason – výčet](../../winscript/reference/breakreason-enumeration.md)   
 [BREAKRESUMEACTION – výčet](../../winscript/reference/breakresumeaction-enumeration.md)