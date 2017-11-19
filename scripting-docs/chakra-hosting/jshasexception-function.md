---
title: "Jshasexception – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsHasException
helpviewer_keywords: JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 32334f4b8787bebaffb9553fcdd40f85334462cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jshasexception-function"></a>JsHasException – funkce
Určuje, zda modul runtime aktuální kontext je ve stavu výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hasException`  
 Jestli modul runtime aktuální kontext je ve stavu výjimka.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud volání do modulu runtime následek výjimku (buď v důsledku spuštění skriptu nebo z důvodu něco jako chyba převodu), modul runtime je umístěn do "stavu výjimky". Všechna volání do jakékoli kontextu vytvořené runtime (s výjimkou výjimek rozhraní API) se nezdaří s `JsErrorInExceptionState` dokud výjimka je zrušeno.  
  
 Pokud modul runtime aktuální kontext je ve stavu výjimky, když zpětné volání se vrátí do modulu, modul se automaticky opětovné výjimku.  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)