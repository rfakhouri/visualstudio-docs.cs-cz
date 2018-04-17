---
title: IDebugEngine3::SetSymbolPath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d5a79cfd817be1a665f0008a39420e7cb39cc50b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
Nastaví cestu nebo cesty, které budou prohledávány pro symboly ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[v] Řetězec obsahující cestu hledání symbolů nebo cesty. Podrobnosti najdete v části "Poznámky". Nemůže mít hodnotu null.|  
|`szSymbolCachePath`|[v] Řetězec obsahující místní cestu, kde můžete mezipaměti symboly. Nemůže mít hodnotu null.|  
|`Flags`|[v] Nepoužívá se; vždy nastaven na hodnotu 0.|  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Řetězec `szSymbolSearchPath` je seznam jedné nebo více cest, oddělené středníky, pro vyhledávání symbolů. Tyto cesty může být místní cesta, cesta UNC stylu nebo adresu URL. Tyto cesty může také jednat o kombinaci různých typů. Pokud se cesta UNC (například \\\Symserver\Symbols), pak modul ladění měli zjistit, pokud je cesta k serveru symbol a bude schopen načíst symboly z tohoto serveru, je do mezipaměti v cestu určenou položkou `szSymbolCachePath`.  
  
 Symbol cesta může také obsahovat jedno nebo více umístění mezipaměti. Mezipaměti jsou uvedená jako první v pořadí podle priority s nejvyšší prioritou mezipaměti a oddělených * symboly. Příklad:  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) metoda provede vlastní operaci načtení symbolů.  
  
## <a name="see-also"></a>Viz také  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)