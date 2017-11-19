---
title: IDebugPortSupplier3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier3
helpviewer_keywords: IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3bd2a46573ca655df3372c33182860cf2d4816d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
Toto rozhraní umožňuje volající k určení, zda portu dodavatele můžete zachovat porty (podle jejich zápis na disk) mezi volání ladicího programu a potom získat seznam zachovaných porty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vlastní port dodavatele implementuje toto rozhraní pro podporu uchování nebo informace o portu při ukládání na disk. Toto rozhraní musí být implementována pro stejný objekt, jako [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](/cpp/atl/queryinterface) na `IDebugPortSupplier2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděno z [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, toto rozhraní podporuje následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Vrátí, zda může být z portu dodavatele zachovat (podle jejich zápis na disk) porty mezi volání ladicího programu.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Vrátí objekt, který slouží k zobrazení výčtu prostřednictvím všechny porty, které byly zapsat na disk dodavatelem tento port.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud port dodavatele můžete zachovávají volání porty, musí toto rozhraní implementovat. Porty by měly být načteny, když dodavatele portu je vytvoření instance a zapsat na disk, když dodavatel port zničena.  
  
 Modul ladění obvykle nekomunikuje s jiného dodavatele portu a bude mít bez použití tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)