---
title: METADATA_ADDRESS_LOCAL | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- METADATA_ADDRESS_LOCAL
helpviewer_keywords:
- METADATA_ADDRESS_LOCAL structure
ms.assetid: 635f6bc5-c486-4e0e-83db-36f15e543843
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 85c763eb9455966f576344a0116cf4a42df0ee18
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53940872"
---
# <a name="metadataaddresslocal"></a>METADATA_ADDRESS_LOCAL
Tato struktura představuje adresu místní proměnné v rámci oboru (obvykle funkce nebo metoda).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_LOCAL {  
   _mdToken  tokMethod;  
   IUnknown* pLocal;  
   DWORD     dwIndex;  
} METADATA_ADDRESS_LOCAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_LOCAL {  
   public int    tokMethod;  
   public object pLocal;  
   public uint   dwIndex;  
}  
```  
  
## <a name="terms"></a>Podmínky  
 tokMethod  
 ID metody nebo funkce lokální proměnná je součástí.  
  
 [C++] `_mdToken` je `typedef` pro 32bitovou verzi `int`.  
  
 pLocal  
 Token jehož adresa představuje tuto strukturu.  
  
 dwIndex  
 Může být index tuto místní proměnnou v metodě nebo funkci nebo jinou hodnotu (specifické pro jazyk).  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, kdy `dwKind` pole `DEBUG_ADDRESS_UNION` struktura je nastavena na `ADDRESS_KIND_LOCAL` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).  
  
 `Warning:` [Jenom C++]  Pokud `pLocal` nemá hodnotu null, pak je nutné volat `Release` na token ukazatel (`addr` je pole v [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura):  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)