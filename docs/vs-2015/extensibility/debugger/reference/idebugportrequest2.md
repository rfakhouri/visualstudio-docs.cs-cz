---
title: IDebugPortRequest2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 211871e0a80e3d9d5f96c4d5735bb18bc1fef213
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254329"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní popisuje port. Tento popis se používá k přidání portu pro dodavatele portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio obvykle implementuje toto rozhraní právě získání portu ladění od jiného dodavatele portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je předána do [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) vytvořit port pro ladění. Volání [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md) vrátí toto rozhraní představující žádost použitý k vytvoření portu na prvním místě.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortRequest2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|Získá název portu, který chcete vytvořit.|  
  
## <a name="remarks"></a>Poznámky  
 Ladicí stroj obvykle nekomunikuje s dodavatele portu a nebude mít žádný použijte pro toto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)

