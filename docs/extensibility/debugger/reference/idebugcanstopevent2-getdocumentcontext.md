---
title: IDebugCanStopEvent2::GetDocumentContext | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::GetDocumentContext
helpviewer_keywords:
- IDebugCanStopEvent2::GetDocumentContext
ms.assetid: 936a6c4e-30c5-4c7e-9ad5-910cc605a4b5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e2e2f9c96780c5b409b8cd145ea554c10e54e96
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960370"
---
# <a name="idebugcanstopevent2getdocumentcontext"></a>IDebugCanStopEvent2::GetDocumentContext
Získá kontext dokumentu, který popisuje umístění této události.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDocumentContext (   
   IDebugDocumentContext2** ppDocCxt  
);  
```  
  
```csharp  
int GetDocumentContext (   
   out IDebugDocumentContext2 ppDocCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDocCxt`  
 [out] Vrátí [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní, které představuje pozici ve zdrojovém souboru dokumentu, který odpovídá aktuální umístění v kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Obecně platí kontext dokumentu můžete představit jako pozici ve zdrojovém souboru.  
  
 Chcete-li získat kontext kódu, který je zaměřeno na kód pokyny, zavolejte [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)