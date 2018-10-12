---
title: IDebugDocumentContext2::Compare | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentContext2::Compare
helpviewer_keywords:
- IDebugDocumentContext2::Compare
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 81ff040788ba1ed353a9d2c413b4fc89aaf0b390
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49250572"
---
# <a name="idebugdocumentcontext2compare"></a>IDebugDocumentContext2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Porovná tento kontext dokumentu do daného pole kontextů dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Compare(   
   DOCCONTEXT_COMPARE       compare,  
   IDebugDocumentContext2** rgpDocContextSet,  
   DWORD                    dwDocContextSetLen,  
   DWORD*                   pdwDocContext  
);  
```  
  
```csharp  
int Compare(   
   enum_ DOCCONTEXT_COMPARE compare,  
   IDebugDocumentContext2[] rgpDocContextSet,  
   uint                     dwDocContextSetLen,  
   out uint                 pdwDocContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `compare`  
 [in] Hodnota z [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md) výčet, který určuje typ porovnání.  
  
 `rgpDocContextSet`  
 [in] Pole [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objekty, které představují dokumentu kontexty porovnávané hodnotě.  
  
 `dwDocContextSetLen`  
 [in] Délka pole kontexty dokumentu k porovnání.  
  
 `pdwDocContext`  
 [out] Vrátí index do `rgpDocContextSet` pole první kontext dokumentu, který vyhovuje porovnání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` Pokud byla nalezena shoda. Vrátí `S_FALSE` Pokud nebyla nalezena žádná shoda. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objekty, které jsou předány jako pole musí být implementované stejné ladicího stroje, který implementuje `IDebugDocumentContext2` objekt volána na; v opačném případě porovnání není platný.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md)

