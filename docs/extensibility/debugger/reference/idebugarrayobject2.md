---
title: IDebugArrayObject2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f5906d0bff268e78d08b82f9f0d65ee6099d0cc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900283"
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Představuje objekt spravovaného pole a umožňuje vyhodnocovače výrazů (EE) k určení základní indexu (dolní meze) pro pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugArrayObject2 : IDebugArrayObject  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 To je implementováno modulem spravovaného ladění (DE).  
  
## <a name="methods"></a>Metody  
 Kromě metod na [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|Získá základní indexy (dolní meze) pro každý index zadaný počet dimenzí v poli.|  
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|Určuje, zda pole má základní indexy (dolní mez).|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní vyhodnocovače výrazů používá k reprezentaci spravovaných polí v strom analýzy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: EE.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll