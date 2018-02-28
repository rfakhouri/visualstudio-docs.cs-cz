---
title: "Iactivescriptdebug – rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptDebug interface
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1e1d0c1cf51c63f1bb3fcd90ae72520da907e50
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptdebug-interface"></a>IActiveScriptDebug – rozhraní
Implementováno modulem skriptovacích strojů, že podpora ladění. Obvykle objekt, který implementuje `IActiveScriptDebug` rozhraní také implementuje `IActiveScript` rozhraní. Pokud je to tento případ, volání `IActiveScript::QueryInterface` metoda získat `IActiveScriptDebug` rozhraní.  
  
 `IActiveScriptDebug` Rozhraní poskytuje možnosti pro:  
  
-   Inteligentního hostitele s převzetím správy dokumentu.  
  
-   Správce ladění proces synchronizace ladění více skriptovacích strojů.  
  
 Kromě metod zděděno z `IUnknown`, `IActiveScriptDebug` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|Vrátí text atributy bloku libovolný text skriptu.|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|Vrací atributy textu pro libovolný skriptlet.|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|Deleguje `IDebugDocumentContext::EnumCodeContexts`.|