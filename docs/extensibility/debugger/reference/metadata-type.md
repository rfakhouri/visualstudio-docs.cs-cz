---
title: METADATA_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: METADATA_TYPE
helpviewer_keywords: METADATA_TYPE structure
ms.assetid: 2d8b78f6-0aef-4d79-809a-cff9b2c24659
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 662dd43e13f842a261d21a656cd73ca64eebcf11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="metadatatype"></a>METADATA_TYPE
Tato struktura Určuje informace o typu pole prováděné z metadat.  
  
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
  
#### <a name="parameters"></a>Parametry  
 ulAppDomainID  
 ID aplikace, ze kterého přišel symbolu. Slouží k jednoznačné identifikaci instance aplikace.  
  
 guidModule  
 Identifikátor GUID modul, který obsahuje toto pole.  
  
 tokClass  
 Metadata tokenu ID tohoto typu.  
  
 [C++] `_mdToken` je `typedef` pro 32bitovou verzi `int`.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura objeví jako součást sjednocení v [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) struktury, kdy `dwKind` pole z `TYPE_INFO` struktura je nastaven na `TYPE_KIND_METADATA` (hodnoty z [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) výčet).  
  
 `tokClass` Hodnota je token metadata, která jednoznačně identifikuje typu. Podrobnosti o tom, jak interpretovat horní bity tokenu ID metadata najdete v tématu `CorTokenType` výčet v souboru corhdr.h ve [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)