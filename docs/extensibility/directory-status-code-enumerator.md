---
title: "Enumerátor kód stavu adresáře | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 998ce86fdf714c65763748971e89fa45ec289a51
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="directory-status-code-enumerator"></a>Enumerátor kód stavu adresáře
`SccDirStatus` Enumerátor obsahuje pojmenované konstantní hodnoty, které určují stav adresáře v systému správy zdrojů. Tento výčet je používán [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md). To byla zavedena ve verzi 1.2 rozhraní API ovládacího prvku Plug-in zdroje.  
  
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
 Nepodařilo se získat stav; Nespoléhejte na něm.  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 Adresář není ve správě zdrojového kódu.  
  
 SCC_DIRSTATUS_CONTROLLED  
 Adresář je ve správě zdrojového kódu.  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 Projekt odpovídající tento adresář je prázdný.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)