---
title: IDebugWindowsComputerPort2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugWindowsComputerPort2 interface
ms.assetid: 25f327b8-0303-4268-88d1-74df630436aa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1e2a037ad0477be258e33879d1dc336fa67cc915
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53965285"
---
# <a name="idebugwindowscomputerport2"></a>IDebugWindowsComputerPort2
Umožňuje dotazování na informace o cílovém počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugWindowsComputerPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno port objekty správce ladění relace.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugWindowsComputerPort2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)|Načte informace o počítači, na kterém běží v ladicím programu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll