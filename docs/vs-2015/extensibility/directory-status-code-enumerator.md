---
title: Enumerátor kódu stavu adresáře | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24f6dde65def4569eb8163d281f872011be0275c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677482"
---
# <a name="directory-status-code-enumerator"></a>Enumerátor kódu stavu adresáře
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [enumerátor kódu stavu adresáře](https://docs.microsoft.com/visualstudio/extensibility/directory-status-code-enumerator).  
  
`SccDirStatus` Obsahuje čítače výčtu s názvem konstantní hodnoty, které určují stav adresáře v systému správy zdrojového kódu. Tento výčet je používán [sccdirqueryinfo –](../extensibility/sccdirqueryinfo-function.md). To byla zavedena ve verzi 1.2 rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
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
 [Sccdirqueryinfo –](../extensibility/sccdirqueryinfo-function.md)

