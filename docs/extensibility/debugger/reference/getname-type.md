---
title: GETNAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GETNAME_TYPE
helpviewer_keywords: GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bb73d39aec7f364ce27ab06ef426d1c4a622878a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugprocess2-getname.md)