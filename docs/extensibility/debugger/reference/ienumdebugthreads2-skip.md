---
title: IEnumDebugThreads2::Skip | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugThreads2::Skip
helpviewer_keywords: IEnumDebugThreads2::Skip
ms.assetid: eab068d4-1f8d-44cd-bc54-92a10fe23de6
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a642553f9b3155226c45fc6a5c3fa2dd1e09a208
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugthreads2skip"></a>IEnumDebugThreads2::Skip
Přeskočí přes zadaný počet elementů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet elementů tak, aby přeskočil.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud `celt` je větší než počet elementů zbývající; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `celt` Určuje hodnotu větší než počet elementů zbývající výčtu nastavena na konci a `S_FALSE` je vrácen.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)