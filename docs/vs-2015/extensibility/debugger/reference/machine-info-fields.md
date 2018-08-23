---
title: MACHINE_INFO_FIELDS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MACHINE_INFO_FIELDS
helpviewer_keywords:
- MACHINE_INFO_FIELDS enumeration
ms.assetid: 2d61d206-7d40-4df1-8c88-1b3c9c78821e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b605022ceb43c22aa0feef328f9925ec150c0a87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668072"
---
# <a name="machineinfofields"></a>MACHINE_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [MACHINE_INFO_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/machine-info-fields).  
  
Určuje, jaké informace se mají načíst pro konkrétní počítač.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_MACHINE_INFO_FIELDS {   
   MCIF_NAME  = 0x00000001,  
   MCIF_FLAGS = 0x00000002,  
   MCIF_ALL   = 0x00000003  
};  
typedef DWORD MACHINE_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_MACHINE_INFO_FIELDS {   
   MCIF_NAME  = 0x00000001,  
   MCIF_FLAGS = 0x00000002,  
   MCIF_ALL   = 0x00000003  
};  
```  
  
## <a name="members"></a>Členové  
 MCIF_NAME  
 Inicializace/použít `bstrName` pole ve struktuře.  
  
 MCIF_FLAGS  
 Inicializace/použít `Flags` pole ve struktuře.  
  
 MIF_ALL  
 Inicializace/použít všechna pole ve struktuře.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md) metoda označíte, kteří členové [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) struktury mají být inicializovány.  
  
 Používá se také v `Fields` člen `MACHINE_INFO` struktury k označení pole, která se používá a je platný.  
  
 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)   
 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)

