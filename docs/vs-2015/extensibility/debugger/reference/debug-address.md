---
title: DEBUG_ADDRESS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 05c6e00591271fc0a8c074e8018bd780c75d1857
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629720"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DEBUG_ADDRESS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debug-address).  
  
Tato struktura představuje adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS {  
   ULONG32             ulAppDomainID;  
   GUID                guidModule;  
   _mdToken            tokClass;  
   DEBUG_ADDRESS_UNION addr;  
} DEBUG_ADDRESS;  
```  
  
```csharp  
public struct DEBUG_ADDRESS {  
   public uint                ulAppDomainID;  
   public Guid                guidModule;  
   public int                 tokClass;  
   public DEBUG_ADDRESS_UNION addr;  
}  
```  
  
## <a name="terms"></a>Podmínky  
 ulAppDomainID  
 ID procesu.  
  
 guidModule  
 Identifikátor GUID modulu, který obsahuje tuto adresu.  
  
 tokClass  
 Token třídy nebo typu tuto adresu.  
  
> [!NOTE]
>  Tato hodnota je specifické pro zprostředkovatele symbolů a proto nemá žádný význam obecné jiných než jako identifikátor pro typ třídy.  
  
 addr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) struktura, která obsahuje sjednocení, struktur, které popisují typy jednotlivých adres. Hodnota `addr`.`dwKind` pochází z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet, který vysvětluje, jak interpretovat sjednocení.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předán [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda být vyplněna.  
  
 **Upozornění [pouze C++]**  
  
 Pokud `addr.dwKind` je `ADDRESS_KIND_METADATA_LOCAL` a pokud `addr.addr.addrLocal.pLocal` není hodnotou null, pak je nutné volat `Release` token ukazatele:  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)

