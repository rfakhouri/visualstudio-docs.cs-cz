---
title: "JsRuntimeAttributes – výčet | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a7917ad5468b8d2924526f953ae444c5d8381eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsruntimeattributes-enumeration"></a>JsRuntimeAttributes – výčet
Atributy modulu runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum JsRuntimeAttributes;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|Modul runtime by měly podporovat přerušení spolehlivé skriptu. Tím se zvyšuje počet míst, kde zkontrolujte modulu runtime pro žádost o přerušení skriptu za cenu malé množství výkon modulu runtime.|  
|`JsRuntimeAttributeDisableBackgroundWork`|Modul runtime nebude provádět žádné pracovní (například uvolňování paměti) na vlákna na pozadí.|  
|`JsRuntimeAttributeDisableEval`|Pomocí `eval` nebo `function` konstruktor vyvolá výjimku.|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|Modul runtime nevygeneruje nativního kódu.|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|Modul runtime povolí všechny povolenými experimentálními funkcemi.|  
|`JsRuntimeAttributeEnableIdleProcessing`|Zavolá hostitele `JsIdle`, takže povolit nečinnosti zpracování. Modul runtime, jinak budou spravovat paměti mírně důkladnějšímu.|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|Volání metody `JsSetException` bude také odesílání výjimkou nástroj script debugger (pokud existuje) poskytnutí ladicího programu šanci na přerušení na výjimku.|  
|`JsRuntimeAttributeNone`|Žádné speciální atributy.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)