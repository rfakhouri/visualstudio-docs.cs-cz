---
title: IDebugPortEx2::GetPortProcessId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1a9cb6a85cd23f0859c8f9ce0aff8c9ef21bf80
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941753"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
Získá ID procesu portu samotný.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwProcessId`  
 [out] Vrátí ID procesu fyzického portu samotný.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V modulu runtime Win32 například tato metoda obvykle volá funkci Win32 `GetCurrentProcessId` získat ID procesu fyzické.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)