---
title: CONSTRUCTOR_ENUM | Dokumentace Microsoftu
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
- CONSTRUCTOR_ENUM
helpviewer_keywords:
- CONSTRUCTOR_ENUM enumeration
ms.assetid: 6d335b2c-66bc-460c-a4a6-4f3f1b697c2c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b455ba8caab9d011497d0d8fc8cbeb7fbc405e9a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627477"
---
# <a name="constructorenum"></a>CONSTRUCTOR_ENUM
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CONSTRUCTOR_ENUM](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/constructor-enum).  
  
Vybere různé druhy konstruktory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
} CONSTRUCTOR_ENUM;  
```  
  
```csharp  
public enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
};  
```  
  
## <a name="members"></a>Členové  
 crAll  
 Vybere všechny konstruktory.  
  
 crNonStatic  
 Vybere nestatické konstruktory.  
  
 crStatic  
 Vybere statické konstruktory.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)

