---
title: IDebugEngine3::SetSymbolPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3::SetSymbolPath
helpviewer_keywords: IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 77a5f294acf60eebc745cb78042e0ea3431fc998
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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