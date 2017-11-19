---
title: IDebugGenericParamField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugGenericParamField interface
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 78ad46b37274a3a2164f3618a1acbce55f0928bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
Reprezentuje parametr pro obecný typ spravovaného kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugGenericParamField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Použít pro podporu obecných typů.  
  
## <a name="methods"></a>Metody  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|Vrátí počet omezení, která jsou přidružená tato obecný parametr.|  
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|Načte omezení, která jsou přidružená tato obecný parametr.|  
|[Getflags –](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|Načte příznaky pro tento obecný parametr.|  
|[Getindex –](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|Načte index tento obecný parametr.|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|Načte název této obecný parametr.|  
|[GetOwner –](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|Načte typ nebo metoda vlastník této obecný parametr.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll