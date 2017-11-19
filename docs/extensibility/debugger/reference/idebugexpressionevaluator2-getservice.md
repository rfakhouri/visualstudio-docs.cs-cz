---
title: IDebugExpressionEvaluator2::GetService | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d907bdd93d2c17eb86ae07f9c9cfa3034fa3c09d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressionevaluator2getservice"></a>IDebugExpressionEvaluator2::GetService
Načte objekt služby zadané svůj jedinečný identifikátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetService (  
   GUID        uid,  
   IUnknown ** ppService  
);  
```  
  
```csharp  
int GetService (  
   Guid       uid,  
   out object ppService  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `uid`  
 [v] Jedinečný identifikátor služby k načtení.  
  
 `ppService`  
 [out] Vrátí objekt, který představuje službu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 To mohou být spotřebovávána vyhodnocování výrazu třetích stran získat services z jiného vyhodnocovací filtr výrazů. Například tato metoda může získat rozhraní pro službu vizualizér z výchozí vyhodnocovací filtr výrazů. Vyhodnocovače výrazů třetí strany se pravděpodobně muset toto rozhraní implementovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)