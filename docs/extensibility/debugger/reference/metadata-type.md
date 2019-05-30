---
title: METADATA_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- METADATA_TYPE
helpviewer_keywords:
- METADATA_TYPE structure
ms.assetid: 2d8b78f6-0aef-4d79-809a-cff9b2c24659
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5aa21d4bfccd50e31c2fd7e76bb8808bba19bc58
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333754"
---
# <a name="metadatatype"></a>METADATA_TYPE
Tato struktura Určuje informace o typ pole z metadat.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagTYPE_METADATA {
   ULONG32  ulAppDomainID;
   GUID     guidModule;
   _mdToken tokClass;
} METADATA_TYPE;
```

```csharp
public struct METADATA_TYPE {
   public uint ulAppDomainID;
   public Guid guidModule;
   public int  tokClass;
};
```

## <a name="parameters"></a>Parametry
 `ulAppDomainID`\
 ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.

 `guidModule`\
 Identifikátor GUID modulu, který obsahuje toto pole.

 `tokClass`\
 ID tokenu metadat tohoto typu.

 [C++] `_mdToken` je `typedef` pro 32bitovou verzi `int`.

## <a name="remarks"></a>Poznámky
 Tato struktura se zobrazí jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturu, kdy `dwKind` pole `TYPE_INFO` struktura je nastavena na `TYPE_KIND_METADATA` (hodnotu z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).

 `tokClass` Hodnotu, která jednoznačně identifikuje typ tokenu metadat. Podrobnosti o tom, jak interpretovat horní bits ID tokenu metadat najdete v tématu `CorTokenType` výčtu v souboru comimage_flags v [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)