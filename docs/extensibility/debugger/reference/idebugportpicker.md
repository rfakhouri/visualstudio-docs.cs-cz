---
title: IDebugPortPicker | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 845e197b186d462b74aaf8cf3cd7218e4606dfc7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716542"
---
# <a name="idebugportpicker"></a>IDebugPortPicker
Představuje vlastní uživatelské rozhraní pro výběr portu.

## <a name="syntax"></a>Syntaxe

```
IDebugPortPicker : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno dodavatelé portů. Dodavatele portu definuje jejich výběr portu vystavení jako identifikátor CLSID a odkazuje `metricPortPickerCLSID` metriky v zveřejněné CLSID.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody objektu `IDebugPortPicker`.

|Metoda|Popis|
|------------|-----------------|
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|Zobrazí zadané dialogové okno, které umožňuje uživateli vybrat port.|
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|Nastaví poskytovatele služeb.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll