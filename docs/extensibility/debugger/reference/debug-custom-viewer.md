---
title: DEBUG_CUSTOM_VIEWER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_CUSTOM_VIEWER
helpviewer_keywords:
- DEBUG_CUSTOM_VIEWER structure
ms.assetid: 8e0ef3f0-0107-48e8-a037-6e52b4c4ed9d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84d8bdc7a4ea9ac59ee0956226618402b397844b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="debugcustomviewer"></a>DEBUG_CUSTOM_VIEWER
Struktura, která identifikuje vlastní prohlížeč nebo zadejte vizualizér.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagDEBUG_CUSTOM_VIEWER {  
   DWORD dwID;  
   BSTR  bstrMenuName;  
   BSTR  bstrDescription;  
   GUID  guidLang;  
   GUID  guidVendor;  
   BSTR  bstrMetric;  
} DEBUG_CUSTOM_VIEWER;  
```  
  
```csharp  
public struct DEBUG_CUSTOM_VIEWER {  
   public uint   dwID;  
   public string bstrMenuName;  
   public string bstrDescription;  
   public Guid   guidLang;  
   public Guid   guidVendor;  
   public string bstrMetric;  
};  
```  
  
## <a name="members"></a>Členové  
 dwID  
 ID k odlišení více prohlížečů nebo vizualizérech implementované jeden `GUID`.  
  
 bstrMenuName  
 Text, který se zobrazí v rozevírací nabídce.  
  
 bstrDescription  
 Popis vlastní prohlížeč nebo typ vizualizér (musí mít hodnotu null Pokud nepoužívá se).  
  
 guidLang  
 Jazyk poskytnete vyhodnocovací filtr výrazů.  
  
 guidVendor  
 Dodavatel poskytnete vyhodnocovací filtr výrazů.  
  
 bstrMetric  
 Metriky, pod kterým vlastní prohlížeč nebo typ vizualizér `CLSID` je uložen.  
  
## <a name="remarks"></a>Poznámky  
 Vrátí seznam tato struktura volání [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) – metoda (a při rozšíření [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) metoda).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)