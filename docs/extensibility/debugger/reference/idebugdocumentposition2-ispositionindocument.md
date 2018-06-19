---
title: IDebugDocumentPosition2::IsPositionInDocument | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
helpviewer_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
ms.assetid: d5cf57cb-b93b-4e1d-bec9-185f4fe8668d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 225a92d521f118c2d038cabf114c69f389af0108
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107261"
---
# <a name="idebugdocumentposition2ispositionindocument"></a>IDebugDocumentPosition2::IsPositionInDocument
Určuje, pokud pozice dokumentu je součástí daného dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsPositionInDocument(   
   IDebugDocument2* pDoc  
);  
```  
  
```csharp  
int IsPositionInDocument(   
   IDebugDocument2 pDoc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDoc`  
 [v] [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) objekt, který reprezentuje obsahující candidate dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se používá hlavně v nastavení zarážek [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) rozhraní. Jako dokumenty jsou načteny, se nazývá pozice zarážek k určení, zda dokument obsahuje této pozice.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)