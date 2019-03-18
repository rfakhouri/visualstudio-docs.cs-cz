---
title: Iactivescriptdebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptDebug interface
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6341b5c3763d6e4c836b3bdc0539552fcbe7f980
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58151021"
---
# <a name="iactivescriptdebug-interface"></a>IActiveScriptDebug – rozhraní
Implementované skriptovacích strojů ukládaných tuto podporu ladění. Obvykle, objekt, který implementuje `IActiveScriptDebug` rozhraní také implementuje `IActiveScript` rozhraní. Pokud tomu tak, `IActiveScript::QueryInterface` metodu k získání `IActiveScriptDebug` rozhraní.  
  
 `IActiveScriptDebug` Rozhraní poskytuje prostředky pro:  
  
- Inteligentní hostitele s převzetím správy dokumentu.  
  
- Správce ladění procesu synchronizace ladění více skriptovací stroje.  
  
  Kromě metod zděděných z `IUnknown`, `IActiveScriptDebug` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|Vrátí text atributy pro libovolný blok textu skriptu.|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|Vrátí text atributy pro libovolného skriptletu.|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|Deleguje se do `IDebugDocumentContext::EnumCodeContexts`.|