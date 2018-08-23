---
title: IEnumCodePaths2 | Dokumentace Microsoftu
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
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8fb38da8a389b8331a04ce26eb6f6ee257cf700
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675405"
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IEnumCodePaths2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumcodepaths2).  
  
Toto rozhraní představuje seznam cest kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumCodePaths2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam cest kódu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) získat toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumCodePaths2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|Načte zadaný počet cest kódu v sekvenci výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|Vynechá zadaný počet cest kódu v sekvenci výčtu.|  
|[Resetovat](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|Získá počet cest kódu v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Cesta kódu představuje volání větev bodu nebo funkce v programu. Seznam cest kódu představuje cestu, přes který provádění kódu obsazené.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)

