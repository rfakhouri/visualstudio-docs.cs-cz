---
title: IDebugGenericParamField | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugGenericParamField interface
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 841331b496aa21687a7ebdf90a6f4eee40b5ae89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674154"
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugGenericParamField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebuggenericparamfield).  
  
Reprezentuje parametr pro obecný typ spravovaného kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugGenericParamField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Používá se pro podporu obecných typů.  
  
## <a name="methods"></a>Metody  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|Vrátí počet omezujících podmínek, které jsou přidruženy tento obecný parametr.|  
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|Získá omezení, které jsou přidruženy tento obecný parametr.|  
|[Getflags –](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|Získá příznaky pro tento obecný parametr.|  
|[Getindex –](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|Načte index tento obecný parametr.|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|Načte název tohoto obecného parametru.|  
|[GetOwner –](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|Načte typ nebo metoda vlastníka tento obecný parametr.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

