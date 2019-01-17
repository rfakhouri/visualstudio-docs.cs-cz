---
title: IActiveScriptParse::InitNew | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.InitNew
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_InitNew
ms.assetid: 3a582bd6-fc0d-43a5-812f-5ea55a8517a1
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0998bea50d7839f93111aa6b116934fae35bfa3
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348981"
---
# <a name="iactivescriptparseinitnew"></a>IActiveScriptParse::InitNew
Inicializuje skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT InitNew(void);  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_FAIL` Pokud během inicializace došlo k chybě.  
  
## <a name="remarks"></a>Poznámky  
 Před použitím skriptovací stroj, jeden z následujících metod musí být volána: `IPersist*::Load`, `IPersist*::InitNew`, nebo `IActiveScriptParse::InitNew`. Sémantika této metody je stejný jako `IPersistStreamInit::InitNew`, v tom, že tato metoda říká skriptovací stroj inicializovat. Všimněte si, že není platný pro volání obou `IPersist*::InitNew` nebo `IActiveScriptParse::InitNew` a `IPersist*::Load`, ani je možné volat `IPersist*::InitNew`, `IActiveScriptParse::InitNew`, nebo `IPersist*::Load` více než jednou.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)