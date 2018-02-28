---
title: IDebugPortRequest2::GetPortName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5906560574836390656254055130af3275fa4f76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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