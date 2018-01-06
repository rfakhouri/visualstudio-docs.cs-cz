---
title: IEnumDebugPorts2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugPorts2
helpviewer_keywords: IEnumDebugPorts2
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 277189c9b5510df1da4802e42225ffafa4b6995c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugports2"></a>IEnumDebugPorts2
Toto rozhraní zobrazí porty dodavatele počítače nebo portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugPorts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vlastní port dodavatele implementuje toto rozhraní představují seznam portů, které jsou vytvořené dodavatele. Visual Studio implementuje toto rozhraní podporu vlastní port dodavatele.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) k získání tohoto rozhraní představující seznam portů, které jsou vytvořené port dodavatele. Volání [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) k získání tohoto rozhraní představující seznam portů, které byly uloženy na disk.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugPorts2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|Načte zadaný počet portů v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|Přeskočí určeného čísla portů v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|Získá počet portů v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio pomocí tohoto rozhraní k naplnění seznamu porty používané pro připojení k procesům.  
  
 Modul ladění obvykle nepoužívá toto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)