---
title: IEnumDebugCodeContexts2::Next | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugCodeContexts2::Next
helpviewer_keywords: IEnumDebugCodeContexts2::Next
ms.assetid: 0d8aa2db-0994-4166-b364-2e25d936fffc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2ac765cfff0333346bec2540bff8d3a20b0ddf19
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugcodecontexts2next"></a>IEnumDebugCodeContexts2::Next
Vrací další sadu elementů z výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Next(  
   ULONG                celt,  
   IDebugCodeContext2** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                 celt,  
   IDebugCodeContext2[] rgelt,  
   ref uint             pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet elementů k načtení. Také určuje maximální velikost `rgelt` pole.  
  
 `rgelt`  
 [ve out] Pole [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) elementy k vyplnění.  
  
 `pceltFetched`  
 [out] Vrátí počet elementů ve skutečnosti, vrátí se v `rgelt`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud méně než požadovaný počet elementů nemohl být vrácen; jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)