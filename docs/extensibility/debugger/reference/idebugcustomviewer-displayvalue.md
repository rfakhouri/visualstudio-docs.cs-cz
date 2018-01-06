---
title: IDebugCustomViewer::DisplayValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomViewer::DisplayValue
helpviewer_keywords: IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 74990eac497b8ed239894121eb954cd8eeca55e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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