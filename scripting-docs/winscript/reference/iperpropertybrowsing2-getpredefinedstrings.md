---
title: IPerPropertyBrowsing2::GetPredefinedStrings | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetPredefinedStrings
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetPredefinedStrings
ms.assetid: d2fa30f7-a566-4dbd-8b47-ffdc00419771
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e07d52eca9434acc7e54f3b35b111cf12af0a871
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794928"
---
# <a name="iperpropertybrowsing2getpredefinedstrings"></a>IPerPropertyBrowsing2::GetPredefinedStrings
Umožňuje volajícímu vyplníte pole se seznamem spočítané pole ukazatele řetězce, které představují potenciální hodnoty této vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetPredefinedStrings(  
   DISPID  dispid,  
   CALPOLESTR*  pCaStrings,  
   CADWORD*  pCaCookies  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dispid`  
 [v] Odesílání identifikátor vlastnosti, pro kterou je volající požadování seznamu řetězec.  
  
 `pCaStrings`  
 [out] Ukazatel na strukturu přidělené volajícího, spočítané pole, který obsahuje element počet a adresu přidělené metoda řadu řetězec ukazatele. Pokud metoda nezdaří, je přidělená není dostatek paměti a obsah struktury není definován.  
  
 `pCaCookies`  
 [out] Ukazatel na strukturu přidělené volajícího, spočítané pole, která obsahuje element počet a adresu metoda přidělené pole typu DWORD. Pokud metoda nezdaří, je přidělená není dostatek paměti a obsah struktury není definován.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Iperpropertybrowsing2 – rozhraní 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)