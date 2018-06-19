---
title: IDebugArrayObject::GetRank | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e76e8d3f39ab5f86ba15db7fd00c4b45fc93c9c2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098586"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
Získá pořadí pole, který je počet dimenzí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwRank`  
 [out] Vrátí pořadí.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Použití [getdimensions –](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) metoda pro načtení velikost Každá dimenze objekt array.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)