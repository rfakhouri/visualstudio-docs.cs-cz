---
title: Enumerátor kódu stavu adresáře | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e082a691a389d5cb9a8fa307a627b11911e0db78
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185253"
---
# <a name="directory-status-code-enumerator"></a>Enumerátor kódu stavu adresáře
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)
