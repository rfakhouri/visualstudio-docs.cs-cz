---
title: IDebugPortPicker::DisplayPortPicker | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 815b44735e36489991da84216e2fcc6db8e6fab4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66308748"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
Zobrazí zadané dialogové okno, které umožňuje uživateli vybrat port.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT DisplayPortPicker(
   HWND hwndParentDialog,
   BSTR* pbstrPortId
);
```

```csharp
public int DisplayPortPicker(
   int hwndParentDialog,
   out string pbstrPortId
);
```

## <a name="parameters"></a>Parametry
`hwndParentDialog`\
[in] Popisovač pro dialogové okno nadřazené.

`pbstrPortId`\
[out] Řetězec identifikátoru portu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrácená hodnota `S_FALSE` (nebo návratovou hodnotu `S_OK` s `BSTR` nastavena na `NULL`) označuje, že uživatel klikl na **zrušit**.

## <a name="see-also"></a>Viz také:
- [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)