---
title: IDebugCustomViewer::DisplayValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 017e1e7a27839dae91559468c62be353bbd43b4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107056"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
Tato metoda je volána k zobrazení se zadanou hodnotou.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DisplayValue(  
   HWND             hwnd,  
   DWORD            dwID,  
   IUnknown *       pHostServices,  
   IDebugProperty3* pDebugProperty);  
);  
```  
  
```csharp  
int DisplayValue(  
   IntPtr          hwnd,   
   uint            dwID,   
   object          pHostServices,   
   IDebugProperty3 pDebugProperty  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hwnd`  
 [v] Nadřazené okno  
  
 `dwID`  
 [v] ID pro vlastní prohlížečů, které podporují víc než jeden typ.  
  
 `pHostServices`  
 [v] Vyhrazena. Vždy nastaven na hodnotu null.  
  
 `pDebugProperty`  
 [v] Rozhraní, které lze použít k načtení hodnoty, který se má zobrazit.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zobrazení se "modální", že tato metoda se vytvořit okno nezbytné, zobrazit hodnotu, čekání na vstup a zavřete okno všechny před vrácením volající. To znamená, že metoda musí zpracovat všechny aspekty zobrazení hodnotu vlastnosti ve vytváření okna pro výstup se čekání na vstup uživatele, likvidace okna.  
  
 Pro podporu změnit hodnotu na danou [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) objekt, můžete použít [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) metoda – Pokud hodnota může být vyjádřený jako řetězec. Jinak, je třeba vytvořit vlastní rozhraní – výhradně pro vyhodnocovací filtr výrazů implementace to `DisplayValue` metoda – na stejný objekt, který implementuje `IDebugProperty3` rozhraní. Toto vlastní rozhraní by zadat metody pro změnu data libovolné velikosti nebo složitost.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)