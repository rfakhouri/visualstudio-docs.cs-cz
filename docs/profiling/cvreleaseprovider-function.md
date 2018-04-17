---
title: Cvreleaseprovider – funkce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a62e590f930baa3e0684fbbf36356cfc607e930
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cvreleaseprovider-function"></a>CvReleaseProvider – funkce
Verze zprostředkovatele značky. Uvolňování poskytovatele značky nebude mít vliv na dříve vytvořenou značky řadu tohoto zprostředkovatele. Značky řady musí být verze samostatně voláním cvreleasemarkerseries –. Chyby k uvolnění zprostředkovatele způsobí, že nevrácenou pamětí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProvider`  
 Kontext zprostředkovatele. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK, když je zprostředkovatel úspěšně vydání nebo kód chyby v případě, že existuje byly všechny chyby. Makra úspěšné nebo NEÚSPĚŠNÉ použijte ke kontrole chybový stav.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)