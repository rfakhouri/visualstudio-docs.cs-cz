---
title: OBJECT_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- OBJECT_TYPE
helpviewer_keywords:
- OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7f0aafc5b41d9020c80cd2b86c9048db1d333bfd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62865437"
---
# <a name="objecttype"></a>OBJECT_TYPE
Určuje typ objektu z vyhodnocovací filtr výrazů.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_OBJECT_TYPE { 
   OBJECT_TYPE_BOOLEAN = 0x0,
   OBJECT_TYPE_CHAR    = 0x1,
   OBJECT_TYPE_I1      = 0x2,
   OBJECT_TYPE_U1      = 0x3,
   OBJECT_TYPE_I2      = 0x4,
   OBJECT_TYPE_U2      = 0x5,
   OBJECT_TYPE_I4      = 0x6,
   OBJECT_TYPE_U4      = 0x7,
   OBJECT_TYPE_I8      = 0x8,
   OBJECT_TYPE_U8      = 0x9,
   OBJECT_TYPE_R4      = 0xa,
   OBJECT_TYPE_R8      = 0xb,
   OBJECT_TYPE_OBJECT  = 0xc,
   OBJECT_TYPE_NULL    = 0xd,
   OBJECT_TYPE_CLASS   = 0xe
};
typedef DWORD OBJECT_TYPE;
```

```csharp
public enum enum_OBJECT_TYPE { 
   OBJECT_TYPE_BOOLEAN = 0x0,
   OBJECT_TYPE_CHAR    = 0x1,
   OBJECT_TYPE_I1      = 0x2,
   OBJECT_TYPE_U1      = 0x3,
   OBJECT_TYPE_I2      = 0x4,
   OBJECT_TYPE_U2      = 0x5,
   OBJECT_TYPE_I4      = 0x6,
   OBJECT_TYPE_U4      = 0x7,
   OBJECT_TYPE_I8      = 0x8,
   OBJECT_TYPE_U8      = 0x9,
   OBJECT_TYPE_R4      = 0xa,
   OBJECT_TYPE_R8      = 0xb,
   OBJECT_TYPE_OBJECT  = 0xc,
   OBJECT_TYPE_NULL    = 0xd,
   OBJECT_TYPE_CLASS   = 0xe
};
```

## <a name="members"></a>Členové
 OBJECT_TYPE_BOOLEAN označuje, že objekt je logická hodnota.

 OBJECT_TYPE_CHAR označuje, že objekt je znak.

 OBJECT_TYPE_I1 označuje, že objekt je celé číslo se znaménkem jeden bajtové.

 OBJECT_TYPE_U1 označuje, že objekt je jeden bajtové číslo bez znaménka.

 OBJECT_TYPE_I2 označuje, že objekt je dva bajty celé číslo se znaménkem.

 OBJECT_TYPE_U2 označuje, že objekt je celé číslo bez znaménka dva bajtu.

 OBJECT_TYPE_I4 označuje, že objekt je celé číslo se znaménkem čtyř bajtů.

 OBJECT_TYPE_U4 označuje, že objekt je celé číslo bez znaménka čtyř bajtů.

 OBJECT_TYPE_I8 znamená, že objekt podepsané celé číslo osm bajtů.

 OBJECT_TYPE_U8 označuje, že objekt je celé číslo bez znaménka osm bajtu.

 OBJECT_TYPE_R4 označuje, že objekt je číslo s plovoucí desetinnou čárkou čtyř bajtů.

 OBJECT_TYPE_R8 označuje, že objekt je číslo s plovoucí desetinnou čárkou osm bajtu.

 OBJECT_TYPE_OBJECT označuje, že objekt je objekt.

 OBJECT_TYPE_NULL označuje, že objekt je NULL.

 OBJECT_TYPE_CLASS znamená, že objekt třídy.

## <a name="remarks"></a>Poznámky
 Předán jako argument [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) a [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) metody.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)
- [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)