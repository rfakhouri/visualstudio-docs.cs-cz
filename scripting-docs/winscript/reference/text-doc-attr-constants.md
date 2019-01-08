---
title: Text_doc_attr – konstanty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- TEXT_DOC_ATTR
apilocation:
- scrobj.dll
helpviewer_keywords:
- TEXT_DOC_ATTR constants
ms.assetid: fd9c53a4-8f73-4c6a-abe5-6b831ecd5b1e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e3fd21ba720dfed394e497a9a56a1bb6898dc60
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097250"
---
# <a name="textdocattr-constants"></a>Konstanty TEXT_DOC_ATTR
Popisují atributy dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef DWORD TEXT_DOC_ATTR;  
```  
  
## <a name="constants"></a>Konstanty  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|TEXT_DOC_ATTR_READONLY|0x00000001|Dokument je jen pro čtení.|  
|TEXT_DOC_ATTR_TYPE_PRIMARY|0x00000002|Dokument je primární soubor tohoto stromu dokumentu.|  
|TEXT_DOC_ATTR_TYPE_WORKER|0x00000004|Dokument je pracovního procesu.|  
|TEXT_DOC_ATTR_TYPE_SCRIPT|0x00000008|Dokument je soubor skriptu.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)