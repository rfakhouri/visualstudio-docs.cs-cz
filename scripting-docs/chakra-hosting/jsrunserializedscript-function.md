---
title: "Jsrunserializedscript – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsRunSerializedScript
helpviewer_keywords: JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b770edbcaa4e7dc36f295407627c10a8b574b88b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsrunserializedscript-function"></a>JsRunSerializedScript – funkce
Spouští serializovaných skript.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `script`  
 Zdrojový kód serializovaných skriptu.  
  
 `buffer`  
 Serializovaná skript.  
  
 `sourceContext`  
 Soubor cookie identifikace skript, který mohou být využívána kontexty debuggable skriptu.  
  
 `sourceUrl`  
 Umístění skriptu pochází.  
  
 `result`  
 Výsledek spuštění skriptu, pokud existuje. Tento parametr může mít hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
 Vyrovnávací paměť není trvalý v paměti skriptovací stroj, aby váš kód musí je udržovat pro zachování připojení, dokud ho může použít ke spuštění skriptů.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)