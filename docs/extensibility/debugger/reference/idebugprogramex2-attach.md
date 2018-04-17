---
title: IDebugProgramEx2::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c58f576a0126472ad60ceeb5fc5289b668bd54dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
Relaci připojení k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který reprezentuje funkce zpětného volání, který modul připojené ladění odesílá události.  
  
 `dwReason`  
 [v] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který je popsaný i důvod pro operace připojení.  
  
 `pSession`  
 [v] Hodnota, která jednoznačně identifikuje relace, který se připojuje k programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby. Tato metoda by měla vrátit `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` Pokud program je již připojen.  
  
## <a name="remarks"></a>Poznámky  
 Port, který obsahuje program můžete použít hodnotu v `pSession` k určení, které relace se pokouší připojit k programu. Například pokud port umožňuje jenom jednu ladicí relace najednou připojit k procesu, port můžete určit, pokud stejné relace je již připojena k jiné programy v procesu.  
  
> [!NOTE]
>  Předaná rozhraní `pSession` má být zpracována pouze jako soubor cookie, hodnotu, která jednoznačně identifikuje správce ladicí relace připojení k tomuto programu; žádné metody na zadaný rozhraní jsou funkční.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)