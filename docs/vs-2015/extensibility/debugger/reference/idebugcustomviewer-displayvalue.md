---
title: IDebugCustomViewer::DisplayValue | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d75ff31ef9ba0ba1badad5cd298b0f8f7220541e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628902"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCustomViewer::DisplayValue](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomviewer-displayvalue).  
  
Tato metoda je volána k zobrazení zadané hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Nadřazené okno  
  
 `dwID`  
 [in] ID pro vlastních prohlížečů, které podporují více než jeden typ.  
  
 `pHostServices`  
 [in] Vyhrazená. Vždy nastavena na hodnotu null.  
  
 `pDebugProperty`  
 [in] Rozhraní, které slouží k načtení hodnoty, který se má zobrazit.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zobrazení je "modal", tato metoda bude vytvoření okna nezbytné, zobrazit hodnotu, počkat na vstup a zavřete okno všechny před vrácením řízení volajícímu. To znamená, že metoda musí zpracovat všechny aspekty zobrazení hodnoty vlastnosti z vytvoření okna pro výstup na čekání na vstup uživatele, chcete-li zničit okno.  
  
 Pro podporu změna hodnoty na daný [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) objektu, můžete použít [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) metoda – Pokud hodnota může být vyjádřený jako řetězec. V opačném případě je potřeba vytvořit vlastní rozhraní – výhradně pro vyhodnocovací filtr výrazů implementace to `DisplayValue` metoda – pro stejný objekt, který implementuje `IDebugProperty3` rozhraní. Toto vlastní rozhraní by poskytla metody pro změnu dat libovolné velikosti nebo složitosti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)

