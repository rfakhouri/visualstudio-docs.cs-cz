---
title: IDebugField::GetSize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetSize
helpviewer_keywords:
- IDebugField::GetSize method
ms.assetid: 73329924-3751-4f44-af54-5986b7943374
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fa10836b91306a99629e80b6869880f018878c38
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919360"
---
# <a name="idebugfieldgetsize"></a>IDebugField::GetSize
Tato metoda načte velikost pole, v bajtech.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetSize( 
   DWORD* pdwSize
);
```

```csharp
int GetSize(
   out uint pdwSize
);
```

#### <a name="parameters"></a>Parametry
 `pdwSize`

 [out] Vrátí velikost.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Všechna pole mít typ a všechny typy mají velikost. Pole typu byte má například velikost 1 bajt.

## <a name="see-also"></a>Viz také
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)