---
title: METADATA_ADDRESS_LOCAL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: METADATA_ADDRESS_LOCAL
helpviewer_keywords: METADATA_ADDRESS_LOCAL structure
ms.assetid: 635f6bc5-c486-4e0e-83db-36f15e543843
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a9d5e32f6f99cddcd3d04d8c10bda958e58fbbf3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="metadataaddresslocal"></a>METADATA_ADDRESS_LOCAL
Tato struktura představuje adresu místní proměnné v oboru (obvykle funkci nebo metodu).  
  
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
 ID metody nebo funkce v místní proměnné je součástí.  
  
 [C++] `_mdToken` je `typedef` pro 32bitovou verzi `int`.  
  
 pLocal  
 Token, jejíž adresa představuje tuto strukturu.  
  
 dwIndex  
 Může být index tento místní proměnné v metody nebo funkce nebo jinou hodnotu (pro specifický jazyk).  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) struktury, kdy `dwKind` pole z `DEBUG_ADDRESS_UNION` struktura je nastaven na `ADDRESS_KIND_LOCAL` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).  
  
 `Warning:`[Pouze C++]  Pokud `pLocal` nemá hodnotu null, pak musí volat `Release` na token ukazatele (`addr` je pole v [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) struktura):  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)