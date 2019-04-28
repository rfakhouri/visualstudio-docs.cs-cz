---
title: IDebugCustomViewer::DisplayValue | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCustomViewer::DisplayValue
helpviewer_keywords:
- IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bda4c60e9164ae195c0e3ba49893b1a818c66f14
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62421369"
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
