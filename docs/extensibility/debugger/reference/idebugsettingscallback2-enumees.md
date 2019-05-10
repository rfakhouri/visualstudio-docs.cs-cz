---
title: IDebugSettingsCallback2::EnumEEs | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::EnumEEs
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 12005f27e533d491451695925253137fb172ccd6
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457615"
---
# <a name="idebugsettingscallback2enumees"></a>IDebugSettingsCallback2::EnumEEs
Vytvoří výčet vyhodnocení výrazu dostupné zadané identifikátory jazyka a dodavatele.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumEEs(
   DWORD  celtBuffer,
   GUID*  rgguidLang,
   GUID*  rgguidVendor,
   DWORD* pceltEEs
);
```

```csharp
public int EnumEEs(
   uint       celtBuffer,
   ref Guid   rgguidLang,
   ref Guid   rgguidVendor,
   ref uint[] pceltEEs
);
```

## <a name="parameters"></a>Parametry
 `celtBuffer`\

 [in] Počet prvků v objektu `pceltEEs` vyrovnávací paměti.

 `rgguidLang`\

 [out v] Jedinečný identifikátor pro programovací jazyk.

 `rgguidVendor`\

 [out v] Jedinečný identifikátor pro dodavatele.

 `pceltEEs`\

 [out v] Pole vyhodnocovače výrazů.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)