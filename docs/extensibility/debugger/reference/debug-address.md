---
title: DEBUG_ADDRESS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 07312208967aeccfbd81f44587f84a43dfebf4c0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101443"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
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
 Identifikátor GUID modul, který obsahuje tuto adresu.  
  
 tokClass  
 Token, určete třídu nebo typ tuto adresu.  
  
> [!NOTE]
>  Tato hodnota je specifický pro zprostředkovatele symbol a proto nemá žádný obecné význam než jako identifikátor pro typ třídy.  
  
 Addr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, která obsahuje spojení struktury, které popisují typy jednotlivých adres. Hodnota `addr`.`dwKind` pochází z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčtu, která vysvětluje, jak interpretovat sjednocení.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předána [getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) metoda k vyplnění.  
  
 **Upozornění [pouze C++]**  
  
 Pokud `addr.dwKind` je `ADDRESS_KIND_METADATA_LOCAL` a pokud `addr.addr.addrLocal.pLocal` není hodnotu null, pak musí volat `Release` na token ukazatele:  
  
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
 [Getaddress –](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)