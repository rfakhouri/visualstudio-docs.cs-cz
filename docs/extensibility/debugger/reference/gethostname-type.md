---
title: GETHOSTNAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GETHOSTNAME_TYPE
helpviewer_keywords: GETHOSTNAME_TYPE enumeration
ms.assetid: 2be92bea-8133-412b-9015-1833baf16e1b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ba4c0eb77d1eb2a902c9db1288785cf2b6d0ac7a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="gethostnametype"></a>GETHOSTNAME_TYPE
Určuje typ názvu hostitele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_GETHOSTNAME_TYPE {   
   GHN_FRIENDLY_NAME = 0,  
   GHN_FILE_NAME     = 1  
};  
typedef DWORD GETHOSTNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETHOSTNAME_TYPE {   
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
 Tyto hodnoty jsou předávány jako argument pro [gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) metoda načíst název hostitele v různých formátech.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)