---
title: Iactivescripterrordebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug interface
ms.assetid: e5d50427-c033-4138-ac6e-3b2dfb3b750a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d773724d23c61aa72b8cd48917f2cd0bef4a7cb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345198"
---
# <a name="iactivescripterrordebug-interface"></a>IActiveScriptErrorDebug – rozhraní
Poskytuje informace o kontextu dokumentu za kompilace chyb a výjimek za běhu. `IActiveScriptError::QueryInterface` Podporuje metodu `IActiveScriptErrorDebug` rozhraní.  
  
 Kromě metod zděděných z `IActiveScriptError`, `IActiveScriptErrorDebug` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptErrorDebug::GetDocumentContext](../../winscript/reference/iactivescripterrordebug-getdocumentcontext.md)|Poskytuje kontext dokumentu pro tuto chybu.|  
|[IActiveScriptErrorDebug::GetStackFrame](../../winscript/reference/iactivescripterrordebug-getstackframe.md)|Poskytuje rámce zásobníku, který je v platnosti pro chyby za běhu.|