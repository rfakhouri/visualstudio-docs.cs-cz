---
title: IDebugDocumentContext2::GetStatementRange | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::GetStatementRange
helpviewer_keywords:
- IDebugDocumentContext2::GetStatementRange
ms.assetid: bc94851a-0ec4-47ea-99c7-0a585e54e726
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c9f03b449142edaa2efc1da0128d4bb4a5b7c901
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdocumentcontext2getstatementrange"></a>IDebugDocumentContext2::GetStatementRange
Získá soubor příkaz rozsahu kontext dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetStatementRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetStatementRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pBegPosition`  
 [ve out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která obsahuje počáteční pozici. Tento argument nastavte na hodnotu null, pokud není nutné tyto informace.  
  
 `pEndPosition`  
 [ve out] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která obsahuje koncovou pozici. Tento argument nastavte na hodnotu null, pokud není nutné tyto informace.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Příkaz rozsah je rozsahu řádků, které poskytly kód, na který odkazuje tento dokument kontext.  
  
 Chcete-li získat rozsahu (včetně komentář) zdrojového kódu v tomto dokumentu kontextu, volejte [getsourcerange –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md) metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchou `CDebugContext` objekt, který zveřejňuje [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní. Tento příklad vyplní koncovou pozici pouze v případě, že počáteční pozice není hodnotu null.  
  
```cpp  
HRESULT CDebugContext::GetStatementRange(TEXT_POSITION* pBegPosition,  
                                         TEXT_POSITION* pEndPosition)    
{    
   HRESULT hr;    
  
   // Check for a valid beginning position argument pointer.    
   if (pBegPosition)    
   {    
      // Copy the member TEXT_POSITION into the local pBegPosition.    
      memcpy(pBegPosition, &m_pos, sizeof (TEXT_POSITION));    
  
      // Check for a valid ending position argument pointer.   
     if (pEndPosition)    
      {    
         // Copy the member TEXT_POSITION into the local pEndPosition.    
         memcpy(pEndPosition, &m_pos, sizeof (TEXT_POSITION));    
      }    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [Getsourcerange –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)