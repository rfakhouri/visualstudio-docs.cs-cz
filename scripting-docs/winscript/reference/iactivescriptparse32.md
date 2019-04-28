---
title: IActiveScriptParse32 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c39c14aa-beb7-4eca-8b8c-2181da1c2e3e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 9f44239b4e423588b8455b93b87e4084a9c7d1c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009313"
---
# <a name="iactivescriptparse32"></a>IActiveScriptParse32
Pokud skript Windows modul umožňuje nezpracovaný text skriptlety kódu mají být přidány do skriptu nebo umožňuje textu výrazu, který se má vyhodnotit v době běhu implementuje `IActiveScriptParse32` rozhraní. Pro interpretované skriptovací jazyky, které mají žádné nezávislé vývojovém prostředí, jako je například jazyk VBScript, to poskytuje alternativní mechanismus (jiné než `IPersist*`) Chcete-li získat kód skriptu do skriptovací stroj a připojit fragmenty skript do různých objektu události.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptParse32::AddScriptlet](../../winscript/reference/iactivescriptparse32-addscriptlet.md)|Přidá skriptlet kódu do skriptu.|  
|[IActiveScriptParse32::InitNew](../../winscript/reference/iactivescriptparse32-initnew.md)|Inicializuje skriptovací stroj.|  
|[IActiveScriptParse32::ParseScriptText](../../winscript/reference/iactivescriptparse32-parsescripttext.md)|Analyzuje daný skriptlet kódu, přidává deklarace do oboru názvů a hodnotí kód podle potřeby.|