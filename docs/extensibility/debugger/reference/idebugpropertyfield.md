---
title: IDebugPropertyField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPropertyField
helpviewer_keywords:
- IDebugPropertyField interface
ms.assetid: b50edb2c-fb8d-4def-993d-17d23d2027c1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 53b89624e1f3b929845411df0261e644191a2db5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpropertyfield"></a>IDebugPropertyField
Toto rozhraní poskytuje funkce, které umožňují načtení a nastavení vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPropertyField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbol pro stejný objekt, který implementuje [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md). Toto rozhraní je specializace, který podporuje koncept vlastnosti třídy.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) získat toto rozhraní z [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda vrátí `FIELD_KIND_PROP`.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)|Získá metody, která se získá vlastnost.|  
|[GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)|Získá metody, která nastaví vlastnost.|  
  
## <a name="remarks"></a>Poznámky  
 Vlastnost je koncept spravovaného kódu a představuje metodu, která se považuje za proměnné. Vlastnosti nejsou k dispozici v nespravované C++.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)