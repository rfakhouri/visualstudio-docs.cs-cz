---
title: GETNAME_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5a0c15f97548386192a635e81a4d0e8a0274cb3a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860397"
---
# <a name="getnametype"></a>GETNAME_TYPE
Určuje název typu souborů, které mají načíst.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
typedef DWORD GETNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
```  
  
## <a name="members"></a>Členové  
 GN_NAME  
 Určuje popisný název dokumentu nebo kontext.  
  
 GN_FILENAME  
 Určuje úplnou cestu dokumentu nebo kontext.  
  
 GN_BASENAME  
 Určuje název základního souboru místo úplnou cestu k dokumentu nebo kontext.  
  
 GN_MONIKERNAME  
 Určuje jedinečný název dokumentu nebo kontext ve formě monikeru.  
  
 GN_URL  
 Určuje název adresy URL dokumentu nebo kontext.  
  
 GN_TITLE  
 Určuje název dokumentu, pokud existuje.  
  
 GN_STARTPAGEURL  
 Získá počáteční adresa URL stránky pro procesy.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány jako parametry [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md), [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md), a [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) metody k určení, jaký typ název, který vrátí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)