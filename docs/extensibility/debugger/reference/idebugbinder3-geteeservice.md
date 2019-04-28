---
title: IDebugBinder3::GetEEService | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder3::GetEEService
helpviewer_keywords:
- IDebugBinder3::GetEEService method
ms.assetid: eb07aa40-8cd9-4a52-a4c7-4affd2307a01
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d709124a392ffb6b6cbbb5a29576a985fe6d0f2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877556"
---
# <a name="idebugbinder3geteeservice"></a>IDebugBinder3::GetEEService
Tato metoda vrátí požadovanou službu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEEService(
   [in] GUID        vendor,
   [in] GUID        language,
   [in] GUID        iid,
   [out] IUnknown** ppService
);
```

```csharp
Int GetEEService(
   Guid       vendor,
   Guid       language,
   Guid       iid,
   out object ppService
);
```

#### <a name="parameters"></a>Parametry
 `vendor`

 [in] `GUID` dodavatele (hodnota null je přijatelná).

 `language`

 [in] `GUID` jazyka (hodnota null je přijatelná).

 `iid`

 [in] `IID` služby získat.

 `ppService`

 [out] Rozhraní pro požadovanou službu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Předání `IID` pro [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md) rozhraní (`IID_IEEVisualizerServiceProvider`) Pokud je k dispozici služba vizualizér typů. Pokud ano, můžete získat vyhodnocovací filtr výrazů [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) rozhraní pro podporu vizualizérů typů. Zobrazit [Visualizing a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti.

## <a name="see-also"></a>Viz také
- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)
- [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)
- [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)