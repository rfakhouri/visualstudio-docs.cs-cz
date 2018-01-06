---
title: IPropertyProxyEESide | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyEESide
helpviewer_keywords: IPropertyProxyEESide interface
ms.assetid: cf227cf8-39d9-4758-8f7e-a697aebb1926
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 90f34e954945f6b557f8c5e1f5ac0b0802e1e663
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ipropertyproxyeeside"></a>IPropertyProxyEESide
Toto rozhraní poskytuje metody pro zobrazení dat na přidruženého objektu. Toto rozhraní je součástí podporu vizualizérech typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IPropertyProxyEESide : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu implementuje toto rozhraní pro podporu vizualizérech typu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) k získání tohoto rozhraní. Volání [QueryInterface](/cpp/atl/queryinterface) na [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní získat [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní implementují následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[InitSourceDataProvider](../../../extensibility/debugger/reference/ipropertyproxyeeside-initsourcedataprovider.md)|Inicializuje Zprostředkovatel zdroje dat, takže lze získat přístup k datům objektu.|  
|[GetManagedViewerCreationData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata.md)|Načte informace o sestavení objektu.|  
|[GetInitialData](../../../extensibility/debugger/reference/ipropertyproxyeeside-getinitialdata.md)|Získá počáteční data pro objekt.|  
|[CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)|Vytvoří kopii uložení dat v existující.|  
|[InPlaceUpdateObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md)|Vytvoří odkaz na existující data úložiště.|  
|[ResolveAssemblyRef](../../../extensibility/debugger/reference/ipropertyproxyeeside-resolveassemblyref.md)|Načte informace o konkrétní sestavení v kontextu sestavení obsahující tohoto objektu.|  
  
## <a name="remarks"></a>Poznámky  
 Vizualizér typu používá toto rozhraní pro přístup k hodnotám přidružená k objektu, který toto rozhraní je součástí. Přístupu k datům prostřednictvím [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) rozhraní, které poskytuje zobrazení jen pro čtení dat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Typ vizualizér a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)