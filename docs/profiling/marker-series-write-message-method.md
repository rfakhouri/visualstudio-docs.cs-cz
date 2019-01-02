---
title: marker_series::write_message – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series::write_message
helpviewer_keywords:
- Concurrency::diagnostic::marker_series::write_message method
ms.assetid: 546121bc-67e0-4a5a-a456-12bd78fd6de2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03a99aa603dec83751a0254897ad9c6f40215016
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53965600"
---
# <a name="markerserieswritemessage-method"></a>marker_series::write_message – metoda
Zapíše zprávu do souboru trasování vizualizátoru souběžnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void write_message(  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `_Format`  
 Složený řetězec formátu, který obsahuje textu smíšeného s nula nebo více položek formátu, který odpovídá objektům v seznamu argumentů.  
  
 `_Importance`  
 Úroveň důležitosti.  
  
 `_Category`  
 Category.Importance úroveň.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *cvmarkersobj.h*  
  
 **Namespace:** Concurrency::Diagnostic –  
  
## <a name="see-also"></a>Viz také:  
 [marker_series – třída](../profiling/marker-series-class.md)