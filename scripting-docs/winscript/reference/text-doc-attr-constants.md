---
title: Text_doc_attr – konstanty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: d22b178d85d304f19e52727ef2c67d77f16da1b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62840080"
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