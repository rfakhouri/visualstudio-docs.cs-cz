---
title: BUILT_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BUILT_TYPE
helpviewer_keywords: BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 34a426853952325f2d1911b7fca55a8f94a6d40f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="builttype"></a>BUILT_TYPE
Tato struktura Určuje informace o typu pole prováděné z metadat.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagTYPE_BUILT {  
   ULONG32      ulAppDomainID;  
   GUID         guidModule;  
   IDebugField* pUnderlyingField;  
} BUILT_TYPE;  
```  
  
```csharp  
public struct BUILT_TYPE {  
   public uint        ulAppDomainID;  
   public Guid        guidModule;  
   public IDebugField pUnderlyingField;  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 ulAppDomainID  
 ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.  
  
 guidModule  
 Identifikátor GUID modul, který obsahuje toto pole.  
  
 pUnderlyingField  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt identifikuje základní pole přidružené k této vytvořené pole.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura objeví jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) struktury, kdy `dwKind` pole z `TYPE_INFO` struktura je nastaven na `TYPE_KIND_BUILT` (hodnoty z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)