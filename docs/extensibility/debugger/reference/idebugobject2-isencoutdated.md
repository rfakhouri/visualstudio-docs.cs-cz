---
title: IDebugObject2::IsEncOutdated | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 757e533f855ab1bc276e484d46d6866b0dd6ca40
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
Tato metoda určuje, zda upravit a pokračovat stav tohoto objektu nebo nadřazeného kontejneru je zastaralý. Tato metoda a vždy vrátí neimplementuje vyhodnocování vlastního výrazu `E_NOTIMPL`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```csharp  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pfEncOutdated`  
 [out] Nenulové hodnoty (`TRUE`), pokud je zastaralý stav upravit a pokračovat, hodnotu (`FALSE`) Pokud není.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
> [!NOTE]
>  Vlastní výraz vyhodnocování musí vracet vždycky `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)