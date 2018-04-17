---
title: IDebugPortRequest2::GetPortName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c81bdc6586766cb4a241bf29e653cb1b10f66f2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
Získá název portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```csharp  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrPortName`  
 [out] Vrací název portu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) rozhraní je obvykle předaný z balíčku ladění (klient) port dodavatele (server) k získání připojení k portu. Balíček ladění a dodavatel port si vědomi možné volby pro port. Pokud řetězec jednoduchý, ale popíše port, pak se `IDebugPortRequest2::GetPortName` metoda má dostatek informací pro připojení. V ostatních případech lze zadat další rozhraní klientem, který lze získat pomocí serveru `IDebugPortRequest2::QueryInterface`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)