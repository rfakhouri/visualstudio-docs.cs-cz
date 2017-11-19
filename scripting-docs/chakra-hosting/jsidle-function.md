---
title: "Jsidle – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsIdle
helpviewer_keywords: JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddffd4f37c0e10985a2dbca26558d8a94b21b2f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsidle-function"></a>JsIdle – funkce
Informuje modulu runtime provést jakékoli zpracování při nečinnosti je potřeba udělat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `nextIdleTick`  
 Další značek systému při bude další nečinnosti práci udělat. Může mít hodnotu null. Vrátí maximální počet rysky Pokud zde žádné nadcházející nečinnosti pracovní postup.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je povoleno zpracování při nečinnosti aktuálního běhového modulu, volání `JsIdle` nečinný hostitele a že modulu runtime můžete provádět úlohy čištění paměti bude informovat aktuálního běhového modulu.  
  
 `JsIdle`Můžete také vrátí počet rysky systému, dokud nebude další nečinnosti práci pro modul runtime udělat. Volání metody `JsIdle` než tento počet značek uplynutí budou dělat žádné kroky.  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)