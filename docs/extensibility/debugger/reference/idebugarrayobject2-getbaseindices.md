---
title: IDebugArrayObject2::GetBaseIndices | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetBaseIndices
- IDebugArrayObject2::GetBaseIndices
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5355e85007c04e523efa4030ca0603a01cf88c68
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62923764"
---
# <a name="idebugarrayobject2getbaseindices"></a>IDebugArrayObject2::GetBaseIndices
Získá základní indexy (dolní meze) pro každý index zadaný počet dimenzí v poli.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetBaseIndices (
   DWORD  dwRank,
   DWORD* dwIndices
);
```

```csharp
int GetBaseIndices (
   uint       dwRank,
   out uint[] dwIndices
);
```

#### <a name="parameters"></a>Parametry
 `dwRank`

 [in] Počet rozměrů (pořadí) pole.

 `dwIndices`

 [out] Základní indexy (dolní meze) pro pole.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Jako příklad, vrátí tato funkce '5' pro pole vytvořené následující C# kódu:

```
int[] lengths = { 12 };
int[] lowerbounds = { 5 };
Array.CreateInstance(typeof(int), lengths, lowerbounds);
```

## <a name="see-also"></a>Viz také
- [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)