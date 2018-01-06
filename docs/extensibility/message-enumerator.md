---
title: "Zpráva enumerátor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enumerator
- source control plug-ins, message enumeration
ms.assetid: 4a4faa0d-d352-40ea-a21d-c09ea286a8e1
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6a24db9c50bd298f068c23af0b6bad5755ec252d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="message-enumerator"></a>Enumerátor zpráv
Následující příznaky se používají pro `TEXTOUTPROC` funkci, která je funkce zpětného volání, která poskytuje rozhraní IDE při volání [SccOpenProject](../extensibility/sccopenproject-function.md) (najdete v části [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) podrobnosti o zpětné volání funkce).  
  
 Pokud IDE se zobrazí výzva k proces zrušit, ale může získat zpráv Storno. V takovém případě zdroj řízení modulu plug-in používá `SCC_MSG_STARTCANCEL` požádat IDE pro zobrazení **zrušit** tlačítko. Potom může být odeslán libovolnou sadu normální zprávy. Pokud platí jedna z těchto vrátí `SCC_MSG_RTN_CANCEL`, pak modul plug-in ukončí operaci a vrátí. Modul plug-in taky dotazuje `SCC_MSG_DOCANCEL` pravidelně k určení, pokud uživatel operaci zrušil. Pokud všechny operace se provádějí, nebo pokud uživatel zrušil, modul plug-in odešle `SCC_MSG_STOPCANCEL`. `SCC_MSG_INFO`, SCC_MSG_WARNING, a SCC_MSG_ERROR typy se používají pro zprávy, které se nezobrazí v posouvání seznam zpráv. `SCC_MSG_STATUS`je speciální typ, který označuje, že text by měl zobrazí v stavový řádek nebo dočasné oblasti. Není trvale zůstanou v seznamu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum {   
   SCC_MSG_RTN_CANCEL = -1,   
   SCC_MSG_RTN_OK = 0,   
   SCC_MSG_INFO = 1   
   SCC_MSG_WARNING,   
   SCC_MSG_ERROR,   
   SCC_MSG_STATUS,   
   SCC_MSG_DOCANCEL,   
   SCC_MSG_STARTCANCEL,   
   SCC_MSG_STOPCANCEL   
};  
```  
  
## <a name="members"></a>Členové  
 SCC_MSG_RTN_CANCEL  
 Vrátí ze zpětného volání k označení zrušit.  
  
 SCC_MSG_RTN_OK  
 Vrátí z zpětné volání pro pokračovat.  
  
 SCC_MSG_INFO  
 Zpráva je informační.  
  
 SCC_MSG_WARNING  
 Zpráva je upozornění.  
  
 SCC_MSG_ERROR  
 Zpráva je chybná.  
  
 SCC_MSG_STATUS  
 Zpráva je určená pro stavový řádek.  
  
 SCC_MSG_DOCANCEL  
 Žádný text; Vrátí IDE `SCC_MSG_RTN_OK` nebo `SCC_MSG_RTN_CANCEL`.  
  
 SCC_MSG_STARTCANCEL  
 Zahájí cyklus Storno.  
  
 SCC_MSG_STOPCANCEL  
 Zastaví smyčky Storno.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)