---
title: Enumerátor kód stavu adresáře | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 539dc4c2ea7b33ce88465f1d8f6651dc890c8e45
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126081"
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