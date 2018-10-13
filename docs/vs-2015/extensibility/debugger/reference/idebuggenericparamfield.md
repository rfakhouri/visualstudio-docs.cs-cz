---
title: IDebugGenericParamField | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
ms.openlocfilehash: cebbcd063b36f875fc1f7e6a6938b0ac86f4e8f8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49265849"
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
|[GetFlags](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|Získá příznaky pro tento obecný parametr.|  
|[GetIndex](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|Načte index tento obecný parametr.|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|Načte název tohoto obecného parametru.|  
|[GetOwner](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|Načte typ nebo metoda vlastníka tento obecný parametr.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

