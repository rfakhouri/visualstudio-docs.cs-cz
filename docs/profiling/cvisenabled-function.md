---
title: Cvisenabled – funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70448c74220c0643654b8cc951bba2d20fb5fdef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cvisenabled-function"></a>CvIsEnabled – funkce
Určuje, zda má jakékoli relace povoleno zadaného zprostředkovatele trasování událostí pro Windows.  
  
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
 Úroveň význam.  
  
 `pProvider`  
 Objekt platný zprostředkovatele. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK, pokud zprostředkovatel je aktuálně povoleno. S_FALSE, pokud zprostředkovatel je aktuálně zakázáno. Kód chyby v případě, že byly všechny chyby. Zkontrolujte pro chybu a pak vyhledejte S_OK/S_FALSE pomocí makro se nezdařilo.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)