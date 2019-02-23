---
title: IDebugSymbolProvider::GetNextAddress | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetNextAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetNextAddress method
ms.assetid: 704eeb94-cb13-49d1-82b6-7d83ed0f19c0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 574111db390388ee1d0c572a3a8825c3a2ae9469
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722756"
---
# <a name="idebugsymbolprovidergetnextaddress"></a>IDebugSymbolProvider::GetNextAddress
Získá adresu ladění, který následuje adresa pro danou ladění v metodě.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetNextAddress( 
   IDebugAddress*  pAddress,
   BOOL            fStatementOnly,
   IDebugAddress** ppAddress
);
```

```csharp
int GetNextAddress( 
   IDebugAddress     pAddress,
   bool              fStatementOnly,
   out IDebugAddress ppAddress
);
```

#### <a name="parameters"></a>Parametry
 `pAddress`

 [in] Adresa pro danou ladění.

 `fStatementOnly`

 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.

 `ppAddress`

 [out] Vrátí adresu další ladění.

## <a name="return-value"></a>Návratová hodnota
 Bude vracet platnou `HRESULT`, obvykle S_OK.

## <a name="see-also"></a>Viz také
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)