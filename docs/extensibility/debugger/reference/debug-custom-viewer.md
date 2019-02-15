---
title: DEBUG_CUSTOM_VIEWER | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DEBUG_CUSTOM_VIEWER
helpviewer_keywords:
- DEBUG_CUSTOM_VIEWER structure
ms.assetid: 8e0ef3f0-0107-48e8-a037-6e52b4c4ed9d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe17c8747d5c678c14561a918ddd9d62bd658841
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315830"
---
# <a name="debugcustomviewer"></a>DEBUG_CUSTOM_VIEWER
Struktura, která identifikuje vlastní prohlížeč nebo zadejte vizualizér.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagDEBUG_CUSTOM_VIEWER {
    DWORD dwID;
    BSTR  bstrMenuName;
    BSTR  bstrDescription;
    GUID  guidLang;
    GUID  guidVendor;
    BSTR  bstrMetric;
} DEBUG_CUSTOM_VIEWER;
```

```csharp
public struct DEBUG_CUSTOM_VIEWER {
    public uint   dwID;
    public string bstrMenuName;
    public string bstrDescription;
    public Guid   guidLang;
    public Guid   guidVendor;
    public string bstrMetric;
};
```

## <a name="members"></a>Členové
dwID  
ID k rozlišení více prohlížečů nebo vizualizéry implementované jeden `GUID`.

bstrMenuName  
Text, který se zobrazí v rozevírací nabídce.

bstrDescription  
Popis vlastní prohlížeč nebo vizualizér typů (musí mít hodnotu null Pokud není využito).

guidLang  
Jazyk poskytující vyhodnocovací filtr výrazů.

guidVendor  
Dodavatel poskytování vyhodnocovací filtr výrazů.

bstrMetric  
Metriky, pod kterým vlastní prohlížeč nebo vizualizér typů `CLSID` uložená.

## <a name="remarks"></a>Poznámky
Seznam tato struktura je vrácený voláním [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) – metoda (a při rozšíření i [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) metoda).

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)  
[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)
