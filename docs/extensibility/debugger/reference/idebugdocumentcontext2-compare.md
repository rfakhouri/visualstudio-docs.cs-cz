---
title: IDebugDocumentContext2::Compare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::Compare
helpviewer_keywords:
- IDebugDocumentContext2::Compare
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f41b0e5973af8e0cb65f093f51137059084c9792
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdocumentcontext2compare"></a>IDebugDocumentContext2::Compare
Porovná tento dokument kontext pro dané pole kontextů dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [v] Hodnota z [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md) výčet, který určuje typ porovnání.  
  
 `rgpDocContextSet`  
 [v] Pole [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objekty, které představují se ve srovnání s kontexty dokumentu.  
  
 `dwDocContextSetLen`  
 [v] Délka pole kontexty dokument k porovnání.  
  
 `pdwDocContext`  
 [out] Vrátí index do `rgpDocContextSet` pole kontext první dokumentu, který splňuje porovnání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` Pokud byla nalezena shoda. Vrátí `S_FALSE` Pokud nebyla nalezena žádná shoda. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objekty, které se předávají v poli musí být implementována stejné ladění modul, který implementuje `IDebugDocumentContext2` objektu, jinak hodnota volána porovnání není platný.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [DOCCONTEXT_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md)