---
title: IPropertyProxyProvider::GetPropertyProxy | Dokumentace Microsoftu
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
- IPropertyProxyProvider::GetPropertyProxy
helpviewer_keywords:
- IPropertyProxyProvider::GetPropertyProxy
ms.assetid: 3ebb7515-5bfe-48f4-9b8d-721b8f664eb6
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9478f9da9c54b950db77d442c1ab6cc4f72b7047
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674152"
---
# <a name="ipropertyproxyprovidergetpropertyproxy"></a>IPropertyProxyProvider::GetPropertyProxy
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IPropertyProxyProvider::GetPropertyProxy](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy).  
  
Načte proxy rozhraní vlastností pro ID zadaný proxy serveru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetPropertyProxy(  
   DWORD                  dwID,  
   IPropertyProxyEESide** proxy  
);  
```  
  
```csharp  
int GetPropertyProxy(  
   uint                     dwID,  
   out IPropertyProxyEESide proxy  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwID`  
 [in] ID proxy požadovanou vlastnost.  
  
 `proxy`  
 [out] Vrátí [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pro podporu externí vizualizátory, tato metoda obvykle předává volání [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md) metody. Zobrazit [Visualizing a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti o jak získat IEEVisualizerService.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)

