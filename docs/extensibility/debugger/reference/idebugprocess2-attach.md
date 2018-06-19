---
title: IDebugProcess2::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::Attach
helpviewer_keywords:
- IDebugProcess2::Attach
ms.assetid: 40d78417-fde2-45c3-96c9-16e06bd9008d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56f14b399a904c2584e81c2b6c8f344654b69a18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31117771"
---
# <a name="idebugprocess2attach"></a>IDebugProcess2::Attach
Připojí správce ladicí relace (SDM) do procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   GUID*                 rgguidSpecificEngines,  
   DWORD                 celtSpecificEngines,  
   HRESULT*              rghrEngineAttach  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback,  
   Guid[]               rgguidSpecificEngines,  
   uint                 celtSpecificEngines,  
   int[]                rghrEngineAttach  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který se používá pro oznámení o události ladění.  
  
 `rgguidSpecificEngines`  
 [v] Pole identifikátorů GUID modulů ladění, který se má použít k ladění aplikace spuštěné v procesu. Tento parametr může mít hodnotu null. Podrobnosti najdete v části poznámky.  
  
 `celtSpecificEngines`  
 [v] Počet ladění motory ve `rgguidSpecificEngines` pole a velikost `rghrEngineAttach` pole.  
  
 `rghrEngineAttach`  
 [ve out] Pole kódy HRESULT vrácený moduly ladění. Velikost toto pole je uveden v `celtSpecificEngines` parametr. Každý kód je obvykle buď `S_OK` nebo `S_ATTACH_DEFERRED`. Ta označuje, zda je DE je aktuálně připojena k žádné programy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Určený proces je již připojen k ladicího programu.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Během procesu připojení došlo k narušení zabezpečení.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Plochy procesu nelze připojit k ladicího programu.|  
  
## <a name="remarks"></a>Poznámky  
 Připojení k procesu pro všechny aplikace spuštěné v tomto procesu, který můžete ladit ladění motory (DE) zadaný v připojí SDM `rgguidSpecificEngines` pole. Nastavte `rgguidSpecificEngines` parametr s hodnotou null hodnotu nebo zahrnují `GUID_NULL` v poli pro připojení k všechny programy v procesu.  
  
 Všechny události ladění, které v průběhu procesu se posílají danou [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objektu. To `IDebugEventCallback2` při SDM volá tuto metodu je zadán objekt.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)