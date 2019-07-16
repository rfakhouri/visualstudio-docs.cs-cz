---
title: IDebugPortPicker | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f3e030facd8c70aec4fdc480b01c90ee4c0acda7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68188393"
---
# <a name="idebugportpicker"></a>IDebugPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Představuje vlastní uživatelské rozhraní pro výběr portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortPicker : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno dodavatelé portů. Dodavatele portu definuje jejich výběr portu vystavení jako identifikátor CLSID a odkazuje `metricPortPickerCLSID` metriky v zveřejněné CLSID.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortPicker`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|Zobrazí zadané dialogové okno, které umožňuje uživateli vybrat port.|  
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|Nastaví poskytovatele služeb.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll
