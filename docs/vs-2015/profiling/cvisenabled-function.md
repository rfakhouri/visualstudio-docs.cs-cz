---
title: Cvisenabled – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvIsEnabledEx
- cvmarkers/CvIsEnabled
helpviewer_keywords:
- CvIsEnabled method
- CvIsEnabledEx method
ms.assetid: 2e4fea6d-758d-4150-8744-6102a1d58c1c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4349d42309482622ae57ba27bb3e675bbdd6a403
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49222466"
---
# <a name="cvisenabled-function"></a>CvIsEnabled – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje, zda všechny relace má povoleno zadaného zprostředkovatele trasování událostí pro Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)



