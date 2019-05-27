---
title: IDebugPortRequest2::GetPortName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 63cda29c6f21cda89742ba218808bc76ffae627a
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204493"
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

## <a name="parameters"></a>Parametry
`pbstrPortName`\
[out] Vrátí název portu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) rozhraní je obvykle předat z balíčku ladění (klient) dodavatele portu (server) k získání připojení k portu. Ladění balíčku a dodavatele portu vědomi zvolit je možné pro port. Pokud řetězec jednoduchého můžete popsat port, pak bude `IDebugPortRequest2::GetPortName` metoda má dostatek informací k vytvoření připojení. Jinak lze zadat další rozhraní klientem, který můžete získat pomocí serveru `IDebugPortRequest2::QueryInterface`.

## <a name="see-also"></a>Viz také:
- [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)