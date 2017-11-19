---
title: "Jsdisableruntimeexecution – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsDisableRuntimeExecution
helpviewer_keywords: JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f44545f7c81344a2d22f0083087f77ac8074278c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsdisableruntimeexecution-function"></a>JsDisableRuntimeExecution – funkce
Pozastaví spuštění skriptu a ukončí všechny spuštěné skripty v modul runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `runtime`  
 Modul runtime pozastaví.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volání do pozastavenou runtime bude neúspěšné, dokud nebude `JsEnableRuntimeExecution` je volána.  
  
 Toto rozhraní API nemá k volání na vlákno, které je aktivní v modulu runtime. I když se modul runtime bude nastavena do stavu pozastavené, okamžitě; nemusí pozastavit provádění skriptu spouštění skriptu bude ukončena s co možná nejdříve k nezachytitelné výjimce.  
  
 Pozastavení provádění v modul runtime, který je již pozastaveno je žádná operace.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)