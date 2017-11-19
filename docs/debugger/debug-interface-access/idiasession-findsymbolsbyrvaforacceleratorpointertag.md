---
title: IDiaSession::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ebeb2ae079845c55c1903afdbcef381a5b4d379c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
Zadané odpovídající hodnota značky, tato metoda vrátí výčet symboly, které jsou obsaženy ve funkci se zakázaným inzerováním akcelerátoru zadaný nadřazený na zadaný relativní virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   DWORD                 rva,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [v] `IDiaSymbol` Odpovídající funkce se zakázaným inzerováním akcelerátoru má proběhnout.  
  
 `tagValue`  
 [v] Hodnota značky ukazatele.  
  
 `rva`  
 [v] Relativní virtuální adresy.  
  
 `ppResult`  
 [out] Ukazatel na `IDiaEnumSymbols` ukazatel rozhraní, který je inicializován s výsledek.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu volat pouze na `IDiaSymbol` rozhraní, která odpovídá funkce se zakázaným inzerováním akcelerátoru.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)