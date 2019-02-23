---
title: IDebugPointerObject::SetBytes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e54a7f38eed85ffe2757b373de1af59e1aaa126b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694723"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
Nastaví hodnotu, na který je odkazováno v řadě po sobě jdoucích bajtů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetBytes( 
   DWORD  dwStart,
   DWORD  dwCount,
   BYTE*  pBytes,
   DWORD* pdwBytes
);
```

```csharp
int SetBytes(
   uint     dwStart,
   uint     dwCount,
   byte[]   pBytes,
   out uint pdwBytes
);
```

#### <a name="parameters"></a>Parametry
 `dwStart`

 [in] Posun v bajtech od začátku objekt odkazoval.

 `dwCount`

 [in] Počet bajtů, které mají nastavit.

 `pBytes`

 [in] Pole bajtů představuje novou hodnotu. Tato hodnota bude uložena do objektu, spuštění na dané pozici.

 `pdwBytes`

 [out] Vrátí že počet bajtů ve skutečnosti nastavit.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda se používá, pokud ukazatel reprezentovaný tímto objektem [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) odkazuje na primitivní typ nebo jednoduchý pole primitivní typy (to znamená, pole, které může být reprezentován jednoduché pořadí bajtů). To `IDebugPointerObject` objektu nemůže být nulový odkaz (musí odkazovat na adresu v paměti).

## <a name="see-also"></a>Viz také
- [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)
- [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)