---
title: IDebugSymbolProvider::GetAddressesFromPosition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: dd01516386d68d3a17d56061f7fcd27109212b6b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
Tato metoda mapuje pozice dokumentu do pole adresy ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
 [v] Umístění dokumentu.  
  
 `fStatmentOnly`  
 [v] V případě hodnoty TRUE omezuje ladění adresy, které mají jeden příkaz.  
  
 `ppEnumBegAddresses`  
 [out] Vrátí enumerátor pro počáteční ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
 `ppEnumEndAddresses`  
 [out] Vrátí [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerátor pro koncovou ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pozice dokumentu obvykle udává určitý rozsah řádků zdroje. Tato metoda poskytuje počáteční a koncové adresy ladění přidružené tyto řádky. Některé jazyky povolit příkazy, které jsou rozmístěny v několika řádky a řádky, které obsahuje více než jeden výraz. Tato metoda poskytuje příznak omezit ladění adresy, které mají jeden příkaz.  
  
 Je možné pro jediný příkaz tak, aby měl více adres ladění, jako v případě šablon.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)