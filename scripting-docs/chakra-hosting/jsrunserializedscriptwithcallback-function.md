---
title: Funkce JsRunSerializedScriptWithCallback | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce51c9473100e71831dd53cc6572d9740790ffa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsrunserializedscriptwithcallback-function"></a>JsRunSerializedScriptWithCallback – funkce
Spouští serializovaných skript.     Poskytuje možnost opožděné zatížení zdroje skriptu, pouze pokud je to potřeba.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `scriptLoadCallback`  
 Zpětné volání voláno, pokud zdrojový kód skriptu, je třeba načíst.  
  
 `scriptUnloadCallback`  
 Zpětné volání volána, když serializovaných skript a zdrojový kód už nejsou potřeba.  
  
 `buffer`  
 Serializovaná skript.  
  
 `sourceContext`  
 Soubor cookie identifikace skript, který mohou být využívána kontexty debuggable skriptu.     Tento kontext bude předána do scriptLoadCallback a scriptUnloadCallback.  
  
 `sourceUrl`  
 Umístění skriptu pochází.  
  
 `result`  
 Výsledek spuštění skriptu, pokud existuje. Tento parametr může mít hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  Toto rozhraní API ještě není k dispozici pro aplikace pro Store.  
  
 Vyžaduje aktivní kontext skriptu.  
  
 Modul runtime bude obsahovat do vyrovnávací paměti, dokud se všechny instance všechny funkce vytvořené z vyrovnávací paměti uvolnění z paměti.  Pak zavolá scriptUnloadCallback k informování volající, který je bezpečné k uvolnění.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)