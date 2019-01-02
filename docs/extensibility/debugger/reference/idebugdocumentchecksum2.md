---
title: IDebugDocumentChecksum2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugDocumentChecksum2 interface
ms.assetid: 6d22fa94-21aa-46cb-b5b5-32a6399ebb20
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 784c8cd4bf762e97b69c6a88ae99701dc993efc5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53921676"
---
# <a name="idebugdocumentchecksum2"></a>IDebugDocumentChecksum2
Představuje kontrolní součet pro ladicí dokumentu a umožňuje předání kontrolní součet mezi komponentami.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentChecksum2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní může být implementováno komponentou, který zpřístupňuje [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní. Ale ho hlavně implementují moduly ladění tak, aby kontrolního součtu vložených v souboru symbol (*.pdb) můžete předán zpět do integrovaného vývojového prostředí a použít při hledání zdroj.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentChecksum2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetChecksumAndAlgorithmId](../../../extensibility/debugger/reference/idebugdocumentchecksum2-getchecksumandalgorithmid.md)|Načte identifikátor dokumentu. kontrolní součet a algoritmus maximální počet bajtů, které mají použít.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll