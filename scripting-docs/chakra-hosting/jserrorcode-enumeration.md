---
title: JsErrorCode – výčet | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b09babd38505c5619f414d2e349cd52b3596ceac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788649"
---
# <a name="jserrorcode-enumeration"></a>JsErrorCode – výčet
Kód chyby vrácený Chakra, který je hostitelem rozhraní API.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
enum JsErrorCode : unsigned int;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="values"></a>Hodnoty  
  
|Název|Popis|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|Kontext nemůžete uvést do stavu ladění, protože je již ve stavu ladění.|  
|`JsErrorAlreadyProfilingContext`|Kontext nelze spustit, profilace, protože je již profilace.|  
|`JsErrorArgumentNotObject`|Hostování rozhraní API, který funguje na hodnoty objektu byla volána s hodnotou jiný objekt.|  
|`JsErrorBadSerializedScript`|Byl použit chybný serializovaných skriptu nebo serializovaných skript byl serializován jinou verzí Chakra stroje.|  
|`JsErrorCannotDisableExecution`|Modul runtime nepodporuje přerušení spolehlivé skriptu.|  
|`JsErrorCannotSerializeDebugScript`|Skripty nelze serializovat v kontextech ladění.|  
|`JsErrorCategoryEngine`|Kategorie chyby, která má vztah k chyby, ke kterým dochází v motoru sám sebe.|  
|`JsErrorCategoryFatal`|Kategorie chyby, které jsou kritické a označují selhání modulu.|  
|`JsErrorCategoryScript`|Kategorie chyby, která má vztah k chyby ve skriptu.|  
|`JsErrorCategoryUsage`|Kategorie chyby, která má vztah k nesprávné použití rozhraní API, sám sebe.|  
|`JsErrorFatal`|Došlo k závažné chybě v modulu.|  
|`JsErrorHeapEnumInProgress`|Výčet haldy právě probíhá v rámci skriptu.|  
|`JsErrorIdleNotEnabled`|Nečinnosti oznámení zadána při hostitele nepovolili zpracování při nečinnosti.|  
|`JsErrorInDisabledState`|Modul runtime je v zakázaném stavu.|  
|`JsErrorInExceptionState`|Modul je ve stavu výjimky a žádné rozhraní API nelze volat, dokud se vymaže výjimku.|  
|`JsErrorInObjectBeforeCollectCallback`|Operace není podporována v objektu před shromažďování zpětné volání.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsErrorInProfileCallback`|Kontext skriptu zrovna profil zpětné volání.|  
|`JsErrorInThreadServiceCallback`|Zpětné volání služby vlákno právě probíhá.|  
|`JsErrorInvalidArgument`|Argument pro hostování rozhraní API byla neplatná.|  
|`JsErrorNoCurrentContext`|Hostování rozhraní API vyžaduje, aby kontextu aktuální, ale neexistuje žádný aktuální kontext.|  
|`JsErrorNotImplemented`|Hostování rozhraní API není dosud implementována.|  
|`JsErrorNullArgument`|Argument pro hostování rozhraní API měl hodnotu null v kontextu, kde není povolena hodnota null.|  
|`JsErrorObjectNotInspectable`|Objekt nemůže být rozbalená k `IInspectable` ukazatel.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsErrorOutOfMemory`|Modul Chakra nemá dostatek paměti.|  
|`JsErrorPropertyNotSymbol`|Hostování rozhraní API, který funguje na symbol vlastnost ID, ale byla zavolána s jiný symbol vlastnost id. Je kód chyby vrácený `JsGetSymbolFromPropertyId` Pokud je tato funkce volána s id vlastnosti bez symbolu.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsErrorPropertyNotString`|Hostování rozhraní API, který funguje na řetězec vlastnost ID, ale byla zavolána s id vlastnosti jiné než řetězec. Kód chyby je vrácen rutinou existující `JsGetPropertyNamefromId` Pokud je tato funkce volána s id vlastnosti jiné než řetězec.<br /><br /> Tato hodnota výčtu je podporována pouze v režimu okraj.|  
|`JsErrorRuntimeInUse`|Modul runtime, který je stále používáno nelze uvolnit.|  
|`JsErrorScriptCompile`|JavaScript kompilace se nezdařila.|  
|`JsErrorScriptEvalDisabled`|Skript byl ukončen, protože se pokusil použít `eval` nebo `function` a zkušební verze byla zakázána.|  
|`JsErrorScriptException`|Při spouštění skriptu došlo k výjimce jazyka JavaScript.|  
|`JsErrorScriptTerminated`|Skript byl ukončen z důvodu požadavek na pozastavení modulu runtime.|  
|`JsErrorWrongRuntime`|Hostování rozhraní API byla volána s objekt vytvořený na různých běhu programu JavaScript.|  
|`JsErrorWrongThread`|Hostování rozhraní API byla volána na nesprávný vlákno.|  
|`JsNoError`|Kód chyby úspěch.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)