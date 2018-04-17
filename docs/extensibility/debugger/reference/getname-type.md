---
title: GETNAME_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 17cd40938d177f3ea74af13bd84fcf1b873dd650
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="getnametype"></a>GETNAME_TYPE
Určuje typ názvu souborů k načtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_GETNAME_TYPE {   
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
public enum enum_GETNAME_TYPE {   
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
 Určuje popisný název dokumentu nebo kontextu.  
  
 GN_FILENAME  
 Určuje úplnou cestu dokumentu nebo kontextu.  
  
 GN_BASENAME  
 Určuje název základního souboru místo úplné cesty dokumentu nebo kontextu.  
  
 GN_MONIKERNAME  
 Určuje jedinečný název dokumentu nebo kontextu ve formě přezdívka.  
  
 GN_URL  
 Určuje název adresy URL dokumentu nebo kontextu.  
  
 GN_TITLE  
 Určuje název dokumentu, pokud nějaká existuje.  
  
 GN_STARTPAGEURL  
 Získá počáteční adresa URL stránky pro procesy.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány jako parametry, které [getName –](../../../extensibility/debugger/reference/idebugdocument2-getname.md), [getName –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md), a [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) metody k určení jaký druh názvu vyhledat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugprocess2-getname.md)