---
title: Scriptlanguageversion – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58aa904a-e3ed-41c6-82d6-e91c8279a792
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aab63989d1ae02f7c75fc9c20a14d59e8a05078
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144508"
---
# <a name="scriptlanguageversion-enumeration"></a>SCRIPTLANGUAGEVERSION – výčet
Určuje možné skriptování verze.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum tagSCRIPTLANGUAGEVERSION{    SCRIPTLANGUAGEVERSION_DEFAULT = 0,    SCRIPTLANGUAGEVERSION_5_7  = 1,    SCRIPTLANGUAGEVERSION_5_8  = 2,    SCRIPTLANGUAGEVERSION_MAX  = 255} SCRIPTLANGUAGEVERSION ;  
```  
  
## <a name="enumeration-values"></a>Hodnoty výčtu  
  
|||  
|-|-|  
|SCRIPTLANGUAGEVERSION_DEFAULT|Výchozí verze. Celočíselná hodnota je 0.|  
|SCRIPTLANGUAGEVERSION_5_7|Windows Scripting verzi 5.7. Celočíselná hodnota je 1.|  
|SCRIPTLANGUAGEVERSION_5_8|Windows Scripting verze 5.8. Celočíselná hodnota je 2.|  
|SCRIPTLANGUAGEVERSION_MAX|Maximální verze. Celočíselná hodnota je 255.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a kódy chyb aktivních skriptů](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)