---
title: IEEVisualizerService::GetValueDisplayStringCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IEEVisualizerService::GetValueDisplayStringCount
- GetValueDisplayStringCount
ms.assetid: d683a833-fbfb-4042-84df-6905124a268a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8af1b785e56d5efba2505b0cdbd5a9474b5c261b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53957946"
---
# <a name="ieevisualizerservicegetvaluedisplaystringcount"></a>IEEVisualizerService::GetValueDisplayStringCount
Získá počet řetězců hodnota má být zobrazen pro zadanou vlastnost nebo pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetValueDisplayStringCount (  
   DWORD         displayKind,   
   IDebugField * propertyOrField,   
   ULONG *       pcelt  
);  
```  
  
```csharp  
int GetValueDisplayStringCount (  
   uint        displayKind,   
   IDebugField propertyOrField,   
   out ulong   pcelt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `displayKind`  
 [in] Hodnota z [DisplayKind](../../../extensibility/debugger/reference/displaykind.md) výčtu.  
  
 `propertyOrField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, které představuje vlastnost nebo pole.  
  
 `pcelt`  
 [out] Vrátí hodnotu řetězce k zobrazení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)