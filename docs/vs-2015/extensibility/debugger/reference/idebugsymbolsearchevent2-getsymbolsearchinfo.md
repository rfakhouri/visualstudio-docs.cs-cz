---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c8ef097ed02ae90b03289e3a2f3a1ad3f0ad8618
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446036"
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Volá obslužnou rutinou události k načtení výsledků o proces načítání symbolů.  
  
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
 [out] IDebugModule3 objekt, který reprezentuje modul, pro kterou byly načteny symboly.  
  
 `pbstrDebugMessage`  
 [out v] Vrátí řetězec obsahující všechny chybové zprávy z modulu. Pokud se nezobrazí žádná chyba, tento řetězec bude obsahovat pouze název modulu ale nikdy je prázdný.  
  
> [!NOTE]
> [C++] `pbstrDebugMessage` nemůže být `NULL` a musí být uvolněna pomocí operátoru `SysFreeString`.  
  
 `pdwModuleInfoFlags`  
 [out] Kombinace příznaků z [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) výčet označující, zda nebyly načteny žádné symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když se obdrží obslužnou rutinu [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) událost po pokusu o načtení symbolů ladění pro modul, obslužná rutina může volat thismethod k určení výsledků zátěž.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)
