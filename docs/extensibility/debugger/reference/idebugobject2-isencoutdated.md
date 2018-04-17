---
title: IDebugObject2::IsEncOutdated | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ab51e2dbc75de33bcafe28295b5e47e4b4358538
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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