---
title: IDebugCodeContext2::GetDocumentContext | Dokumentace Microsoftu
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
- IDebugCodeContext2::GetDocumentContext
helpviewer_keywords:
- IDebugCodeContext2::GetDocumentContext
ms.assetid: d552cc92-963f-43c1-949f-ae6b63a427b8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6f68bb0b855fa5e5fcc6cc2e81bd14c8f491abf6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629717"
---
# <a name="idebugcodecontext2getdocumentcontext"></a>IDebugCodeContext2::GetDocumentContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCodeContext2::GetDocumentContext](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext).  
  
Získá kontext dokumentu, který odpovídá tento kontext kódu. Kontext dokumentu představuje pozici ve zdrojovém souboru, který odpovídá zdrojový kód, který vygeneroval tento pokyn.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetDocumentContext(   
   IDebugDocumentContext2** ppSrcCxt  
);  
```  
  
```csharp  
int GetDocumentContext(   
   out IDebugDocumentContext2 ppSrcCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppSrcCxt`  
 [out] Vrátí [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) objekt, který odpovídá kontext kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Obecně platí kontext dokumentu můžete představit jako pozici ve zdrojovém souboru kontext kódu je pozice instrukce pro kód ve službě stream provádění.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)

