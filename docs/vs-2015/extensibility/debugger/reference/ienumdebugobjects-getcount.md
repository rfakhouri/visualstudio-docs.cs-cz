---
title: IEnumDebugObjects::GetCount | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugObjects::GetCount
helpviewer_keywords:
- IEnumDebugObjects::GetCount method
ms.assetid: 9cbc5db4-03ae-479f-a664-13cad66ad210
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9478ac84637bc76bed42488931b2457ab5aadf7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49178019"
---
# <a name="ienumdebugobjectsgetcount"></a>IEnumDebugObjects::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda vrátí počet prvků ve výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcelt`  
 [out] Vrátí počet prvků ve výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, která určuje, že je potřeba je implementovat pouze další, klonování, přeskočit a obnovení.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)

