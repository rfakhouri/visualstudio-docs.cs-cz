---
title: PDB_TYPE | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PDB_TYPE
helpviewer_keywords:
- PDB_TYPE structure
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ad4b6a06a2a145daa85d780f4d23dfac9bebf7a0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205102"
---
# <a name="pdbtype"></a>PDB_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato struktura Určuje informace o typ pole z symbolů ze souboru PDB.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct _tagTYPE_PDB {  
   ULONG32 ulAppDomainID;  
   GUID    guidModule;  
   DWORD   symid;  
} PDB_TYPE;  
```  
  
```csharp  
public struct PDB_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public uint symid;  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 ulAppDomainID  
 ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.  
  
 guidModule  
 Identifikátor GUID modulu, který obsahuje toto pole.  
  
 symid  
 ID symbol, který odpovídá do tohoto pole.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura se zobrazí jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) strukturu, kdy `dwKind` pole `TYPE_INFO` struktura je nastavena na `TYPE_KIND_PDB` (hodnotu z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
