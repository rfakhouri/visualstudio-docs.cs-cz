---
title: IDebugComPlusSymbolProvider::AreSymbolsLoaded | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AreSymbolsLoaded
- IDebugComPlusSymbolProvider::AreSymbolsLoaded
ms.assetid: bbf8707d-f89c-4177-b019-d519f1ec6f4a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e0a45fe635ccfebb6895048d6e29d81b393171e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680741"
---
# <a name="idebugcomplussymbolprovideraresymbolsloaded"></a>IDebugComPlusSymbolProvider::AreSymbolsLoaded
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugComPlusSymbolProvider::AreSymbolsLoaded](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider-aresymbolsloaded).  
  
Určuje, pokud jsou načteny symboly ladění pro zadaný modul zadaný identifikátor domény aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT AreSymbolsLoaded (  
   ULONG32 ulAppDomainID,  
   GUID    guidModule  
);  
```  
  
```csharp  
int AreSymbolsLoaded (  
   uint ulAppDomainID,  
   Guid guidModule  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ulAppDomainID`  
 [in] Identifikátor pro doménu aplikace.  
  
 `guidModule`  
 [in] Jedinečný identifikátor pro modul.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud jsou načteny symboly ladění, vrátí `S_OK`; v opačném případě vrátí `S_FALSE`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugSymbolProvider** objekt, který zveřejňuje [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) rozhraní.  
  
```cpp#  
HRESULT CDebugSymbolProvider::AreSymbolsLoaded(  
    ULONG32 ulAppDomainID,  
    GUID guidModule  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::AreSymbolsLoaded );  
  
    IfFalseGo( GetModule( idModule, &pModule ) == S_OK, S_FALSE );  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::AreSymbolsLoaded, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

