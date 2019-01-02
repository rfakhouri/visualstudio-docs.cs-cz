---
title: Enumerátor kódu stavu adresáře | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a8d6a541415e42e8d35dc4f3ab814c89cf939beb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53927607"
---
# <a name="directory-status-code-enumerator"></a>Enumerátor kódu stavu adresáře
`SccDirStatus` Obsahuje čítače výčtu s názvem konstantní hodnoty, které určují stav adresáře v systému správy zdrojového kódu. Tento výčet je používán [sccdirqueryinfo –](../extensibility/sccdirqueryinfo-function.md). To byla zavedena ve verzi 1.2 rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>Členové  
 SCC_DIRSTATUS_INVALID  
 Nebylo možné získat stav; Nespoléhejte na to.  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 Adresář není pod správou zdrojových kódů.  
  
 SCC_DIRSTATUS_CONTROLLED  
 Adresář je pod správou zdrojových kódů.  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 Projekt odpovídající tento adresář je prázdný.  
  
## <a name="see-also"></a>Viz také:  
 [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)