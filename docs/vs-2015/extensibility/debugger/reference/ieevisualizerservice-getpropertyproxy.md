---
title: IEEVisualizerService::GetPropertyProxy | Dokumentace Microsoftu
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
- IEEVisualizerService::GetPropertyProxy
helpviewer_keywords:
- IEEVisualizerService::GetPropertyProxy method
ms.assetid: 748750f4-76e7-4580-9da2-afba07681b37
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a66916aea87129ff0e77bb906a996d6c603ad770
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667158"
---
# <a name="ieevisualizerservicegetpropertyproxy"></a>IEEVisualizerService::GetPropertyProxy
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEEVisualizerService::GetPropertyProxy](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy).  
  
Tato metoda vrátí proxy pro objekt vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [in] ID vlastnosti proxy pro načtení.  
  
 `proxy`  
 [out] Požadované implementované v proxy serveru [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) předá žádost v této metodě jako součást své podpory vizualizérů typů.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)

