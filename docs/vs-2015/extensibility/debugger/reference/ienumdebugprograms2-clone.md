---
title: IEnumDebugPrograms2::Clone | Dokumentace Microsoftu
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
- IEnumDebugPrograms2::Clone
helpviewer_keywords:
- IEnumDebugPrograms2::Clone
ms.assetid: 880846c2-39d3-45cd-85c3-ad5409a3710f
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 90b7f5bcb685f1c8810476ae6066150ae366484c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49301077"
---
# <a name="ienumdebugprograms2clone"></a>IEnumDebugPrograms2::Clone
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vrátí kopii objektu do aktuálního výčtu jako samostatný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugPrograms2** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugPrograms2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí kopii objektu tento výčet jako samostatný objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kopírování výčet má stejného stavu jako původní v době, kdy tato metoda je volána. Ale tuto kopii a původní stavy jsou oddělené a je možné změnit individuálně.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)

