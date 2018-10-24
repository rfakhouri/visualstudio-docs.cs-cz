---
title: IDebugPortRequest2::GetPortName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 047cd8e9643f976e78b49f7636b5daa156ad7d60
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49837149"
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá název portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [out] Vrátí název portu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) rozhraní je obvykle předat z balíčku ladění (klient) dodavatele portu (server) k získání připojení k portu. Ladění balíčku a dodavatele portu vědomi zvolit je možné pro port. Pokud řetězec jednoduchého můžete popsat port, pak bude `IDebugPortRequest2::GetPortName` metoda má dostatek informací k vytvoření připojení. Jinak lze zadat další rozhraní klientem, který můžete získat pomocí serveru `IDebugPortRequest2::QueryInterface`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)

