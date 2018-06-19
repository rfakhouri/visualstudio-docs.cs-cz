---
title: Funkce JsParseSerializedScriptWithCallback | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15f531783c7a1018340be8033261a58418d0f515
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788550"
---
# <a name="jsparseserializedscriptwithcallback-function"></a>JsParseSerializedScriptWithCallback – funkce
Analyzuje serializovaných skript a vrátí funkci, představující skript.     Poskytuje možnost opožděné zatížení zdroje skriptu, pouze pokud je to potřeba.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsParseSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_ JsValueRef * result  
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
 Funkce představující kód skriptu.  
  
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