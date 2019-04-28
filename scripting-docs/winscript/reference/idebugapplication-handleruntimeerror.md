---
title: IDebugApplication::HandleRuntimeError | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.HandleRuntimeError
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::HandleRuntimeError
ms.assetid: f8f3bbaf-09e5-4d01-8a35-f380bc7ff8ed
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c2c9a8b15b5095ac346ba047d6668aada7647a31
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63412437"
---
# <a name="idebugapplicationhandleruntimeerror"></a>IDebugApplication::HandleRuntimeError
Způsobí, že chcete blokovat aktuální vlákno a odešle oznámení o chybě integrovaného vývojového prostředí v ladicím programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT HandleRuntimeError(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   IActiveScriptSite*        pScriptSite,  
   BREAKRESUMEACTION*        pbra,  
   ERRORRESUMEACTION*        perra,  
   BOOL*                     pfCallOnScriptError  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pErrorDebug`  
 [in] Chyba, ke které došlo.  
  
 `pScriptSite`  
 [in] Skript lokality vlákna.  
  
 `pbra`  
 [out] Akce se má provést, když ladicí program pokračuje v aplikaci.  
  
 `perra`  
 [out] Akce se má provést, když ladicí program pokračuje aplikace, pokud dojde k chybě.  
  
 `pfCallOnScriptError`  
 [out] Příznak, který je `TRUE` Pokud modul by měly volat `IActiveScriptSite::OnScriptError` metody.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Modul jazyka volá tuto metodu v kontextu vlákna, které způsobí chybu za běhu. Tato metoda způsobí, že chcete blokovat aktuální vlákno a odešle oznámení o chybě k odeslání do ladicího programu integrovaného vývojového prostředí. Když ladicí program IDE obnoví aplikace, vrátí tato metoda s akcí, jež mají být provedeny.  
  
> [!NOTE]
> Při selhání za běhu může být volána modul jazyka ve vláknu provádět tyto úkoly, jako výčet rámců zásobníku nebo vyhodnocení výrazů.  
  
## <a name="see-also"></a>Viz také  
 [Idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)   
 [Iactivescripterrordebug – rozhraní](../../winscript/reference/iactivescripterrordebug-interface.md)   
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)   
 [Breakresumeaction – výčet](../../winscript/reference/breakresumeaction-enumeration.md)   
 [ERRORRESUMEACTION – výčet](../../winscript/reference/errorresumeaction-enumeration.md)