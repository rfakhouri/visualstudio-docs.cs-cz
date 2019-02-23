---
title: IDebugArrayField::GetRank | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1c091c7696867f369262a81259105dcf23fbe4c9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698154"
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

#### <a name="parameters"></a>Parametry
 `pdwRank`

 [out] Vrátí počet rozměrů.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Rozměr pole odpovídá počet rozměrů. V jazyce C++ a C# vícerozměrná pole jsou ve skutečnosti pole polí a může proto považovat jenom jednorozměrná pole (a `GetRank` metoda vždy vrátí hodnotu 1). V [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], na druhé straně vícerozměrná pole jsou zpracovány jinak a pořadí těchto pole odpovídá počet rozměrů (a `GetRank` metoda vždy vrátí počet dimenzí).

## <a name="see-also"></a>Viz také
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)