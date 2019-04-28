---
title: IDebugSymbolProvider::GetAddressesFromPosition | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 27349cfdc438da133c4cea05077649ebb4df376c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547153"
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda mapuje umístění dokumentu do pole adresy ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocPos`  
 [in] Pozice dokumentu.  
  
 `fStatmentOnly`  
 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.  
  
 `ppEnumBegAddresses`  
 [out] Vrátí enumerátor pro počáteční ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
 `ppEnumEndAddresses`  
 [out] Vrátí [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerátor pro koncové adresy ladění přidružené k tomuto prohlášení nebo řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pozice dokumentu obvykle udává určitý rozsah řádků zdroje. Tato metoda poskytuje počáteční a koncovou adresu ladění přidružené tyto řádky. Některé jazyky povolit příkazy, které zahrnují více řádků nebo řádky, které obsahuje více než jeden výraz. Tato metoda poskytuje příznak, který chcete omezit adresy ladění, které mají jeden příkaz.  
  
 Je možné mít víc adres ladění, jako v případě šablon jeden příkaz.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
