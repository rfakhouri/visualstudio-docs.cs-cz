---
title: IDebugProcess2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::Attach
helpviewer_keywords: IDebugProcess2::Attach
ms.assetid: 40d78417-fde2-45c3-96c9-16e06bd9008d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 47b14c3de6b5b9980e2ad420596a1243e84c8882
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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