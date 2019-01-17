---
title: Source_text_attr – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SOURCE_TEXT_ATTR constants
ms.assetid: 459384b0-1463-4841-a2b3-a993207163bf
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc5e7a7bb6c91bd852a8fd2024b708166c085209
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349774"
---
# <a name="sourcetextattr-enumeration"></a>SOURCE_TEXT_ATTR – výčet
Popisují atributy jednoho znaku zdrojového textu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_SOURCE_TEXT_ATTR{    SOURCETEXT_ATTR_KEYWORD    = 0x0001,    SOURCETEXT_ATTR_COMMENT    = 0x0002,    SOURCETEXT_ATTR_NONSOURCE    = 0x0004,    SOURCETEXT_ATTR_OPERATOR   = 0x0008,    SOURCETEXT_ATTR_NUMBER    = 0x0010,    SOURCETEXT_ATTR_STRING    = 0x0020,    SOURCETEXT_ATTR_FUNCTION_START  = 0x0040};  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Hodnota|Popis|  
|------------|-----------|-----------------|  
|SOURCETEXT_ATTR_KEYWORD|0x0001|Znak, který je součástí klíčové slovo jazyka, například klíčové slovo jazyka VBScript `While`.|  
|SOURCETEXT_ATTR_COMMENT|0x0002|Znak, který je součástí blok komentáře.|  
|SOURCETEXT_ATTR_NONSOURCE|0x0004|Znak, který není součástí kompilované jazyk zdrojového textu. Například HTML okolní blok skriptu.|  
|SOURCETEXT_ATTR_OPERATOR|0x0008|Znak, který je součástí operátor jazyka. Příklad:, aritmetický operátor **+**.|  
|SOURCETEXT_ATTR_NUMBER|0x0010|Znak, který je součástí číselnou konstantu jazyka.  Například konstanty 3,14159.|  
|SOURCETEXT_ATTR_STRING|0x0020|Znak, který je součástí jazyka řetězcová konstanta. Například řetězec "Hello World".|  
|SOURCETEXT_ATTR_FUNCTION_START|0x0040|Znak, který označuje začátek bloku funkce|  
  
## <a name="remarks"></a>Poznámky  
 Obvykle `IDebugDocumentHost::GetScriptTextAttributes`, `IActiveScriptDebug::GetScriptletTextAttributes`, a `IActiveScriptDebug::GetScriptTextAttributes` metody vrátí jeden atribut text na znak, pokud:  
  
-   Je nastavený příznak GETATTRTYPE_DEPSCAN, v takovém případě může metoda vrátit příznaky SOURCETEXT_ATTR_IDENTIFIER a SOURCETEXT_ATTR_MEMBERLOOKUP  
  
-   Je nastavený příznak GETATTRFLAG_THIS, v takovém případě může metoda vrátit příznak SOURCETEXT_ATTR_THIS  
  
-   Je nastavený příznak GETATTRFLAG_HUMANTEXT, v takovém případě může metoda vrátit SOURCETEXT_ATTR_HUMANTEXT příznak.  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)