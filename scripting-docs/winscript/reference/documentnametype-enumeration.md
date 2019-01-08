---
title: Documentnametype – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DOCUMENTNAMETYPE
apilocation:
- scrobj.dll
helpviewer_keywords:
- DOCUMENTNAMETYPE enumeration
ms.assetid: d36d550e-efb4-493d-8971-4de267005654
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31e304cfbb0ed7cd19b832d7ed7c33ccc2c930c3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094767"
---
# <a name="documentnametype-enumeration"></a>Výčet DOCUMENTNAMETYPE
Popisuje, jaký typ získat pro dokument.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagDOCUMENTNAMETYPE {  
   DOCUMENTNAMETYPE_APPNODE,  
   DOCUMENTNAMETYPE_TITLE,  
   DOCUMENTNAMETYPE_FILE_TAIL,  
   DOCUMENTNAMETYPE_URL,  
DOCUMENTNAMETYPE_UNIQUE_TITLE,} DOCUMENTNAMETYPE;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|DOCUMENTNAMETYPE_APPNODE|Získává název se zobrazí ve stromu aplikace.|  
|DOCUMENTNAMETYPE_TITLE|Získá název, jak je zobrazen v záhlaví okna prohlížeče.|  
|DOCUMENTNAMETYPE_FILE_TAIL|Získá název souboru bez cesty.|  
|DOCUMENTNAMETYPE_URL|Získá adresu URL dokumentu.|  
|DOCUMENTNAMETYPE_UNIQUE_TITLE|Získá název s výčtu pro identifikaci.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)