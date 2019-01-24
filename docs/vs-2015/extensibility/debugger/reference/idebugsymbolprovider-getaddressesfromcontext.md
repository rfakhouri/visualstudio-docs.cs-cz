---
title: IDebugSymbolProvider::GetAddressesFromContext | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ebd36bdda5059a4fd3c0334a5a2f222aaae40f01
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54757008"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda mapuje kontext dokumentu do pole adresy ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocContext`  
 [in] Kontext dokumentu.  
  
 `fStatmentOnly`  
 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.  
  
 `ppEnumBegAddresses`  
 [out] Vrátí enumerátor pro počáteční ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
 `ppEnumEndAddresses`  
 [out] Vrátí [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerátor pro koncové adresy ladění přidružené k tomuto prohlášení nebo řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext dokumentu obvykle udává určitý rozsah řádků zdroje. Tato metoda poskytuje počáteční a koncovou adresu ladění přidružené tyto řádky. Některé jazyky povolit příkazy, které zahrnují více řádků nebo řádky, které obsahuje více než jeden výraz. Tato metoda poskytuje příznak, který chcete omezit adresy ladění, které mají jeden příkaz.  
  
 Je možné mít víc adres ladění, jako v případě šablon jeden příkaz.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
