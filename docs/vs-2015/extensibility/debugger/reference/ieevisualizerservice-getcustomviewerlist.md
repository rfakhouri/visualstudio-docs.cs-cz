---
title: IEEVisualizerService::GetCustomViewerList | Dokumentace Microsoftu
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
- IEEVisualizerService::GetCustomViewerList
helpviewer_keywords:
- IEEVisualizerService::GetCustomViewerList method
ms.assetid: 249d26ca-914f-43af-a400-8162477223f4
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e037ac728c47b2b4610d866b2ba3868dc44b4eb0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629626"
---
# <a name="ieevisualizerservicegetcustomviewerlist"></a>IEEVisualizerService::GetCustomViewerList
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEEVisualizerService::GetCustomViewerList](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist).  
  
Tato metoda vrátí seznam hodnot vizualizérů typů, které tato služba ví o.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCustomViewerList(  
   ULONG                celtSkip,  
   ULONG                celtRequested,  
   DEBUG_CUSTOM_VIEWER* rgViewers,  
   ULONG*               pceltFetched  
);  
```  
  
```csharp  
int GetCustomViewerList(  
   uint                  celtSkip,  
   uint                  celtRequested,  
   DEBUG_CUSTOM_VIEWER[] rgViewers,  
   out uint              pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celtSkip`  
 [in] Počet vizualizéry mají přeskočit.  
  
 `celRequested`  
 [in] Počet vizualizéry k načtení (také určuje velikost `rgViewers` pole).  
  
 `rgViewers`  
 [out v] Pole [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) struktury být vyplněna.  
  
 `pceltFetched`  
 [out] Počet vizualizéry skutečně načtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) předá žádost v této metodě jako součást své podpory vizualizérů typů. Pokud se chyba při vyhodnocování výrazu také poskytuje vlastních prohlížečů pro stejného typu, můžete připojit odpovídajícím způsobem vyplněný [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) struktur těchto vlastních prohlížečů do seznamu. Ujistěte se, že [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) odráží tyto další prohlížeče.  
  
 Zobrazit [vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) podrobnosti o rozdílech mezi vizualizérů a prohlížeče.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)   
 [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md)   
 [Vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)

