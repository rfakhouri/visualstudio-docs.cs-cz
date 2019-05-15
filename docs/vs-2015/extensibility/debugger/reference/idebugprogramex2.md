---
title: IDebugProgramEx2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramEx2
helpviewer_keywords:
- IDebugProgramEx2 interface
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2d3abc956d736f5c9273134b41c0fc9c2dc7db62
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65688932"
---
# <a name="idebugprogramex2"></a>IDebugProgramEx2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní umožňuje relace ladění správci připojit k programu a získat uzel program přidružený k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní na stejný objekt jako [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, aby bylo možné nechat SDM, zatímco ve stejnou dobu umožní dodavatele portu můžete sledovat všechny relace připojen k připojení k programu program. Pokud zvolí dodavatele port. Tento vlastní port toto rozhraní implementovat.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání SDM [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na `IDebugProgram2` rozhraní k získání tohoto rozhraní ke sledování relací, které jste připojili k programy.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramEx2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|Program připojí k relaci.|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|Získá uzel program přidružený k programu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je privátní mezi SDM a program.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Portpriv.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
