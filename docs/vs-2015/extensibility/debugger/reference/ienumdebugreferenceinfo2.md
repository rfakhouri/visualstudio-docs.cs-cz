---
title: IEnumDebugReferenceInfo2 | Dokumentace Microsoftu
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
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 891022c12d3fe463c165653b5bf0b054efa751d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667243"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEnumDebugReferenceInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugreferenceinfo2).  
  
Vytvoří výčet toto rozhraní [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugReferenceInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní jako součást jeho podporu pro odkazy na objekty v paměti. Toto rozhraní musí být implementované jenom v případě, že jsou podporovány odkazy.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Visual Studio volání [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) získat toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugReferenceInfo2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|Načte zadaný počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v sekvenci výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|Vynechá zadaný počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v pořadí výčtu.|  
|[Resetovat](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|Získá počet [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Odkaz je v podstatě typu a adresu, že vlastnost je název, typ a adresu. Odkaz se uchovávají jako objekt uvedené existuje v paměti. Zobrazit [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) další podrobnosti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)

