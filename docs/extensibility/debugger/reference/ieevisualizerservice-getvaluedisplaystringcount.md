---
title: IEEVisualizerService::GetValueDisplayStringCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IEEVisualizerService::GetValueDisplayStringCount
- GetValueDisplayStringCount
ms.assetid: d683a833-fbfb-4042-84df-6905124a268a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b3ed52e8be77e5f4dce081fc6a60ae22cecbb990
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56720095"
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
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)