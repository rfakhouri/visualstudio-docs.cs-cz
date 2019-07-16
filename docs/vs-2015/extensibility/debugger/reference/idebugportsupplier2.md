---
title: IDebugPortSupplier2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2
helpviewer_keywords:
- IDebugPortSupplier2 interface
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b6d9c3f8b45affd192d4109db08454345dcd0814
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68188232"
---
# <a name="idebugportsupplier2"></a>IDebugPortSupplier2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní poskytuje porty pro správce ladění relace (SDM).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní k reprezentaci dodavatele portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání `CoCreateInstance` s dodavatele portu `GUID` vrátí toto rozhraní (to je typické způsob, jak získat toto rozhraní). Příklad:  
  
```cpp#  
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)  
{  
    IDebugPortSupplier2 *pPS = NULL;  
    if (pPortSupplierGuid != NULL) {  
        CComPtr<IDebugPortSupplier2> spPortSupplier;  
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);  
        if (spPortSupplier != NULL) {  
            pPS = spPortSupplier.Detach();  
        }  
    }  
    return (pPS);  
}  
```  
  
 Volání [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) vrátí toto rozhraní představující aktuální dodavatele portu, která je používána ve [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md) vrátí toto rozhraní představující dodavatele portu, který vytvořili port.  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) představuje seznam `IDebugPortSupplier` rozhraní ( `IEnumDebugPortSuppliers` rozhraní se získávají z [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md), značila všechno dodavatelé portů zaregistrovaného [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]).  
  
 Ladicí stroj obvykle nekomunikuje s dodavatele portu.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortSupplier2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|Získá název dodavatele portu.|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|Získá identifikátor dodavatele portu.|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|Získá od jiného dodavatele portu port.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|Vytvoří výčet porty, které už existují.|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|Ověřuje, že dodavatele portu podporuje přidání nové porty.|  
|[AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|Přidá port.|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|Odebere port.|  
  
## <a name="remarks"></a>Poznámky  
 Dodavatele portu můžete identifikovat podle názvu a ID, přidat a odebrat porty a výčet všechny porty, které poskytuje dodavatele portu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
