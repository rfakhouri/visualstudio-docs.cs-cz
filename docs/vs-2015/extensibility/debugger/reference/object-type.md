---
title: OBJECT_TYPE | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- OBJECT_TYPE
helpviewer_keywords:
- OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fc23045fa70554133eba3a7f1326681bf31ea379
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205144"
---
# <a name="objecttype"></a>OBJECT_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje typ objektu z vyhodnocovací filtr výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 OBJECT_TYPE_BOOLEAN  
 Označuje, že objekt je logická hodnota.  
  
 OBJECT_TYPE_CHAR  
 Označuje, že objekt je znak.  
  
 OBJECT_TYPE_I1  
 Označuje, že objekt je celé číslo se znaménkem jeden bajtové.  
  
 OBJECT_TYPE_U1  
 Označuje, že objekt je jeden bajtové číslo bez znaménka.  
  
 OBJECT_TYPE_I2  
 Označuje, že objekt je dva bajty celé číslo se znaménkem.  
  
 OBJECT_TYPE_U2  
 Označuje, že objekt je celé číslo bez znaménka dva bajtu.  
  
 OBJECT_TYPE_I4  
 Označuje, že objekt je celé číslo se znaménkem čtyř bajtů.  
  
 OBJECT_TYPE_U4  
 Označuje, že objekt je celé číslo bez znaménka čtyř bajtů.  
  
 OBJECT_TYPE_I8  
 Označuje, že objekt je podepsané celé číslo osm bajtů.  
  
 OBJECT_TYPE_U8  
 Označuje, že objekt je celé číslo bez znaménka osm bajtu.  
  
 OBJECT_TYPE_R4  
 Označuje, že objekt je číslo s plovoucí desetinnou čárkou čtyř bajtů.  
  
 OBJECT_TYPE_R8  
 Označuje, že objekt je číslo s plovoucí desetinnou čárkou osm bajtu.  
  
 OBJECT_TYPE_OBJECT  
 Označuje, že objekt je objekt.  
  
 OBJECT_TYPE_NULL  
 Označuje, že objekt je NULL.  
  
 OBJECT_TYPE_CLASS  
 Označuje, že objekt je třída.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) a [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)
