---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 518429149ad1d997b860e486f3db4e519ef42cae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
Volá obslužnou rutinou události a načtěte výsledky o procesu zatížení symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
   IDebugModule3**    pModule,  
   BSTR*              pbstrDebugMessage,  
   MODULE_INFO_FLAGS* pdwModuleInfoFlags  
);  
```  
  
```csharp  
int GetSymbolSearchInfo(  
   IDebugModule3              pModule,   
   ref string                 pbstrDebugMessage,   
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags  
);  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `pModule`  
 [out] Objekt IDebugModule3 reprezentující modul, u kterého byly načteny symboly.  
  
 `pbstrDebugMessage`  
 [ve out] Vrací řetězec obsahující všechny chybové zprávy z modulu. Pokud se nezobrazí žádná chyba, pak tento řetězec bude obsahovat jenom název modulu ale nikdy je prázdný.  
  
> [!NOTE]
>  [C++] `pbstrDebugMessage` nemůže být `NULL` a musí být uvolněno s `SysFreeString`.  
  
 `pdwModuleInfoFlags`  
 [out] Kombinace příznaků z [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) výčet označující, zda byly načteny žádné symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud obslužná rutina obdrží [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) událostí po pokusu o načtení symboly pro ladění pro modul obslužná rutina může volat thismethod k určení výsledky této zatížení.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)