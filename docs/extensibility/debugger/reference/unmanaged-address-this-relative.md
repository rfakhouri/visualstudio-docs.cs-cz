---
title: UNMANAGED_ADDRESS_THIS_RELATIVE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9d2bf87a804295a5ea8f6750ee9cd93643c53bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913007"
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
Tato struktura představuje adresu, která je vzhledem k `this` ukazatel (`Me` v jazyce Visual Basic).

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagUNMANAGED_THIS_RELATIVE {
   DWORD dwOffset;
   DWORD dwBitOffset;
   DWORD dwBitLength;
} UNMANAGED_ADDRESS_THIS_RELATIVE;
```

```csharp
public struct UNMANAGED_THIS_RELATIVE {
   public uint dwOffset;
   public uint dwBitOffset;
   public uint dwBitLength;
}
```

## <a name="terms"></a>Podmínky
 dwOffset posun bajtu od základní umístění (například začátek třídy vtable).

 dwBitOffset posun v bitech od základní pozice (vždy 0 Pokud odkazující na bitové pole).

 Počet bitů představující adresu dwBitLength (vždy 0 Pokud odkazující na bitové pole).

## <a name="remarks"></a>Poznámky
 Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, kdy `dwKind` pole `DEBUG_ADDRESS_UNION` struktura je nastavena na `ADDRESS_KIND_UNMANAGED_THIS_RELATIVE` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)