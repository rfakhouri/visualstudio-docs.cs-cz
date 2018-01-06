---
title: IEnumDebugAddresses::Next | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugAddresses::Next
helpviewer_keywords: IEnumDebugAddresses::Next method
ms.assetid: 941e4be7-858d-433a-9259-18d0d017be9e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c1af74bb556c6250d3df4a32603ab323bffe6da2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugaddressesnext"></a>IEnumDebugAddresses::Next
Tato metoda vrátí další sadu elementů z výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Next(  
   ULONG           celt,  
   IDebugAddress** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint            celt,  
   IDebugAddress[] rgelt,  
   ref uint        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet elementů k načtení. Také určuje maximální velikost `rgelt` pole.  
  
 `rgelt`  
 [ve out] Pole [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) elementy k vyplnění.  
  
 `pceltFetched`  
 [out] Vrátí počet elementů ve skutečnosti, vrátí se v `rgelt`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud méně než požadovaný počet elementů nemohl být vrácen; jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)