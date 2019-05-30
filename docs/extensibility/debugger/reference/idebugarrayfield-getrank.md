---
title: IDebugArrayField::GetRank | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 33d5118ffa045ccc2315ccb596850be6922fc2ed
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321679"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
Získá pořadí nebo počet rozměrů pole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

## <a name="parameters"></a>Parametry
`pdwRank`\
[out] Vrátí počet rozměrů.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Rozměr pole odpovídá počet rozměrů. V jazyce C++ a C# vícerozměrná pole jsou ve skutečnosti pole polí a může proto považovat jenom jednorozměrná pole (a `GetRank` metoda vždy vrátí hodnotu 1). V [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], na druhé straně vícerozměrná pole jsou zpracovány jinak a pořadí těchto pole odpovídá počet rozměrů (a `GetRank` metoda vždy vrátí počet dimenzí).

## <a name="see-also"></a>Viz také:
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)