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
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955026"
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