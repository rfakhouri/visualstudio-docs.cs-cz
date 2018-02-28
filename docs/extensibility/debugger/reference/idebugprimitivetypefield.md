---
title: IDebugPrimitiveTypeField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugPrimitiveTypeField interface
ms.assetid: 73a428fd-797e-4ceb-8392-ba16f1c5226b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5e18b62d8d655729e47a2616d8a5eae9dae19e76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprimitivetypefield"></a>IDebugPrimitiveTypeField
Reprezentuje hodnotu primitivní typ výčtu ze [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPrimitiveTypeField : IDebugField  
```  
  
## <a name="methods"></a>Metody  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetPrimitiveType](../../../extensibility/debugger/reference/idebugprimitivetypefield-getprimitivetype.md)|Načte primitivní typ přidružený k toto pole.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll