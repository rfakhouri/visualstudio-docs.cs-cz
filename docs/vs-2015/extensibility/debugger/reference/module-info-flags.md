---
title: MODULE_INFO_FLAGS | Dokumentace Microsoftu
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
- MODULE_INFO_FLAGS
helpviewer_keywords:
- MODULE_INFO_FLAGS enumeration
ms.assetid: e22d3723-b4d4-4524-8a2f-3adb55bbd273
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 33ae24e6ce67e9998140ac3146c1f3ce3b325561
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675294"
---
# <a name="moduleinfoflags"></a>MODULE_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [MODULE_INFO_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-info-flags).  
  
Určuje stav symbolů pro modul.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
typedef DWORD MODULE_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
```  
  
## <a name="members"></a>Členové  
 MIF_SYMBOLS_LOADED  
 Aspoň jedna sada symboly byl načten modulem (jinak nebyly načteny žádné symboly).  
  
## <a name="remarks"></a>Poznámky  
 Tato hodnota je vrácený [getsymbolsearchinfo –](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getsymbolsearchinfo –](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)

