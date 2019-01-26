---
title: IDebugSymbolProviderDirect | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugSymbolProviderDirect interface
ms.assetid: 872b04a8-70de-4ab5-aceb-684c81828545
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dcbee53b2f3d0a5a4fc45ab7e55bbb2a0cbe106a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931125"
---
# <a name="idebugsymbolproviderdirect"></a>IDebugSymbolProviderDirect
Představuje zprostředkovatele symbol, který má přímý přístup do metadat a základní rozhraní symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugSymbolProviderDirect: IUnknown  
```  
  
## <a name="methods"></a>Metody  
 Toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetAppIDFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getappidfromaddress.md)|Načte identifikátor domény aplikace podle první adresy ladění.|  
|[GetCurrentModulesInfo](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesinfo.md)|Načte informace o modulech ve skupině symbol.|  
|[GetCurrentModulesState](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesstate.md)|Načte informace o skupině symbol, který poskytovatel symbolů je jejím členem.|  
|[GetMetaDataImport](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmetadataimport.md)|Načte informace o import metadat.|  
|[GetMethodFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmethodfromaddress.md)|Načte informace o metodě na adrese zadaný ladění.|  
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getsymunmanagedreader.md)|Načte modul pro načítání symbolů pro nespravovaný kód.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je možné použít místo většinu dalších rozhraní poskytovatele symbolů. Poskytuje přímý přístup k metadatům a `CorSym` rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll