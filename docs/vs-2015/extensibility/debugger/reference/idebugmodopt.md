---
title: IDebugModOpt | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 66f499225d2b319f3678c88894a1217d90b10135
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162522"
---
# <a name="idebugmodopt"></a>IDebugModOpt
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Představuje volitelný modifikátor ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získané z [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt, který reprezentuje třídy nebo metody.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|Načte seznam volitelné modifikátory.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: SH.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll
