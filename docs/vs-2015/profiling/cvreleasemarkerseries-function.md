---
title: Cvreleasemarkerseries – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8df22a27f23395ac3de6bb3b4f28c7746dd10ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668885"
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [cvreleasemarkerseries – funkce](https://docs.microsoft.com/visualstudio/profiling/cvreleasemarkerseries-function).  
  
Uvolní značky řady. Nepoužívejte objekt řady značky po uvolnění jinak aplikace, mohou selhat. Nepodařilo se uvolnit značky řady způsobí, že nevracení paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMarkerSeries`  
 Adresa proměnné objektu zprostředkovatele. Adresa nesmí být NULL, proměnná může mít libovolnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při řady značky se úspěšně uvolnily nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)



