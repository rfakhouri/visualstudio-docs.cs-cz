---
title: IDebugTypeFieldBuilder | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugTypeFieldBuilder interface
ms.assetid: 2dfed0be-6972-4bec-baec-f0b78df9ef97
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 90ed594ff8b6c8f3811b61fe68b2d2ab16a9a017
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53962072"
---
# <a name="idebugtypefieldbuilder"></a>IDebugTypeFieldBuilder
Představuje možnost vytvořit pole, které představuje typ.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugTypeFieldBuilder : IUnknown  
```  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získávají z poskytovatel symbolů.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CreatePrimitive](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createprimitive.md)|Vytvoří objekt, který představuje primitivního typu.|  
|[CreatePointerToType](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createpointertotype.md)|Vytvoří ukazatel na zadaného typu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: SH.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll