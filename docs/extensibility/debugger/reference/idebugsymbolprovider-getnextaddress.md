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
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8ea45e3aa1f59353e0a395a61b0309144b413227
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223987"
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

## <a name="parameters"></a>Parametry
 `pAddress`\

 [in] Adresa pro danou ladění.

 `fStatementOnly`\

 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.

 `ppAddress`\

 [out] Vrátí adresu další ladění.

## <a name="return-value"></a>Návratová hodnota
 Bude vracet platnou `HRESULT`, obvykle S_OK.

## <a name="see-also"></a>Viz také:
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)