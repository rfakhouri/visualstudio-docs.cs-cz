---
title: IDebugDocumentContext2::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentContext2::Compare
helpviewer_keywords: IDebugDocumentContext2::Compare
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 550695aa52f1c913b25fc56975eb5c6e36b4c091
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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