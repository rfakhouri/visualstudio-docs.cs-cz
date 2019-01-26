---
title: marker_series::write_flag – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersojb/Concurrency::diagnostic::marker_series::write_flag
helpviewer_keywords:
- Concurrency::diagnostic::marker_series::write_flag method
ms.assetid: ca07f388-e5d5-46fd-b991-fe6e9029a68f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f70f6b357e8baaf721c751c57b21924afaff90e6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069774"
---
# <a name="markerserieswriteflag-method"></a>marker_series::write_flag – metoda
Příznak, který zapisuje do souboru trasování vizualizátoru souběžnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void write_flag(  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
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
 Kategorie.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *cvmarkersobj.h*  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Viz také:  
 [marker_series – třída](../profiling/marker-series-class.md)