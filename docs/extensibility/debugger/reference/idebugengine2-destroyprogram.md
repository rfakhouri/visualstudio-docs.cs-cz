---
title: IDebugEngine2::DestroyProgram | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::DestroyProgram
helpviewer_keywords:
- IDebugEngine2::DestroyProgram
ms.assetid: 0c9e2698-c70f-4770-a7bb-39650e9c3a1f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8e85eb457a16de03fa989d86109a8705c3b36174
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105863"
---
# <a name="idebugengine2destroyprogram"></a>IDebugEngine2::DestroyProgram
Informuje o ladění modulu (DE) zda zadaný program byla atypicky ukončena a zda je DE musí vyčistit všechny odkazy na program a odesílání program odstraňte událost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DestroyProgram(   
   IDebugProgram2* pProgram  
);  
```  
  
```cpp  
int DestroyProgram(   
   IDebugProgram2 pProgram  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgram`  
 [v] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program, který atypicky byla ukončena.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Po tato metoda je volána, DE následně odešle [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) událostí zpět do správce ladicí relace (SDM).  
  
 Tato metoda není implementována (vrátí `E_NOTIMPL`) Pokud je DE běží v rámci jednoho procesu s programem laděné. Tato metoda je implementována pouze v případě, že je DE běží v rámci jednoho procesu jako SDM.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)