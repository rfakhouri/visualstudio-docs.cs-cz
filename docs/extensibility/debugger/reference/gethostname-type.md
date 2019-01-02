---
title: GETHOSTNAME_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- GETHOSTNAME_TYPE
helpviewer_keywords:
- GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 82705ad50d5dca6c3c20758663163832b5da8179
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53862910"
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
Určuje typ názvu hostitele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
typedef DWORD GETHOSTNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
```  
  
## <a name="members"></a>Členové  
 GHN_FRIENDLY_NAME  
 Určuje popisný název hostitele.  
  
 GHN_FILE_NAME  
 Určuje název souboru hostitele.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány jako argument [gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) metodu pro načtení názvu hostitele v různých formátech.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)