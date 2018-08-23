---
title: IDebugComPlusSymbolProvider::GetEntryPoint | Dokumentace Microsoftu
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
- IDebugComPlusSymbolProvider::GetEntryPoint
- GetEntryPoint
ms.assetid: 9640e121-1da1-41f9-8e66-76efca36baf2
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4594d4a4770d5540e4bf4f91fc147de02283aac2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667464"
---
# <a name="idebugcomplussymbolprovidergetentrypoint"></a>IDebugComPlusSymbolProvider::GetEntryPoint
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugComPlusSymbolProvider::GetEntryPoint](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider-getentrypoint).  
  
Načte vstupní bod aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetEntryPoint(  
   ULONG32         ulAppDomainID,  
   GUID            guidModule,  
   IDebugAddress** ppAddress  
);  
```  
  
```csharp  
int GetEntryPoint(  
   uint              ulAppDomainID,  
   Guid              guidModule,  
   out IDebugAddress ppAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ulAppDomainID`  
 [in] Identifikátor pro doménu aplikace.  
  
 `guidModule`  
 [in] Jedinečný identifikátor pro modul.  
  
 `ppAddress`  
 [out] Vrátí vstupní bod, který je reprezentován [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugSymbolProvider** objekt, který zveřejňuje [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) rozhraní.  
  
```cpp#  
HRESULT CDebugSymbolProvider::GetEntryPoint(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IDebugAddress **ppAddress  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidWritePtr(ppAddress, IDebugAddress *));  
  
    METHOD_ENTRY( CDebugSymbolProvider::GetEntryPoint );  
  
    IfFalseGo( ppAddress, E_INVALIDARG );  
  
    *ppAddress = NULL;  
  
    IfFailGo( GetModule( idModule, &pModule) );  
  
    IfFailGo( pModule->GetEntryPoint( ppAddress ) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::GetEntryPoint, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

