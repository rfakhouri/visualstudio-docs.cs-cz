---
title: Cvisenabled – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvIsEnabledEx
- cvmarkers/CvIsEnabled
helpviewer_keywords:
- CvIsEnabled method
- CvIsEnabledEx method
ms.assetid: 2e4fea6d-758d-4150-8744-6102a1d58c1c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8af4da802ef0ad87831f2f67f47e8ffb66a969e7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54990040"
---
# <a name="cvisenabled-function"></a>Cvisenabled – funkce
Určuje, zda všechny relace má povoleno zadaného zprostředkovatele trasování událostí pro Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```C  
HRESULT CvIsEnabled(  
   _In_ PCV_PROVIDER pProvider  
);  
HRESULT CvIsEnabledEx(  
   _In_ PCV_PROVIDER pProvider,  
   _In_ CV_IMPORTANCE level,  
   _In_ int category  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `category`  
 Kategorie.  
  
 `level`  
 Úroveň důležitosti.  
  
 `pProvider`  
 Objekt zprostředkovatele platné. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK, pokud zprostředkovatel je aktuálně povoleno. S_FALSE, pokud zprostředkovatel je momentálně zakázané. Kód chyby v případě, že došlo k chybám. Použijte makro se nezdařilo pro kontrolu chybovou podmínku a pak vyhledejte hodnotu S_OK/S_FALSE.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** *cvmarkers.h*  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)