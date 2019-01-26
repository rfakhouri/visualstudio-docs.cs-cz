---
title: IDebugPortNotify2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 13b96fd88bee0bff70352606325917cb1dd4229a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021725"
---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
Toto rozhraní zaregistruje nebo zruší registraci program, který lze ladit s portem, který je spuštěn na.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortNotify2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní pro podporu přidávání a odebírání programů z portu. Obvykle je implementované na stejný objekt, který implementuje [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugPort2` rozhraní vrátí toto rozhraní. Kromě toho volání [GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md) vrátí toto rozhraní. Ladicí stroj můžete zobrazit toto rozhraní jako parametr [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortNotify2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|Zaregistruje port, který je spuštěn na program, který lze ladit.|  
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|Zruší registraci program, který lze ladit z portu, který je spuštěn na.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud není port pro ladění je způsob, jak zjistit, když programy jsou načteny nebo uvolněny, dodavatel port. Tento vlastní port musí implementovat toto rozhraní. Všechny programy, které jsou načteny pro ladění přes konkrétní port jsou sledovány v tomto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)