---
title: IDiaSession::findSymbolsByRVAForAcceleratorPointerTag | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad2a0656b03fb057b631319e922a83605fa62a6e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859461"
---
# <a name="idiasessionfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
Odpovídající hodnota značky zadány, tato metoda vrátí výčet symboly, které jsou obsaženy ve funkci se zakázaným inzerováním akcelerátor zadaný nadřazený prvek na zadaný relativní virtuální adrese.  
  
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
 [in] `IDiaSymbol` , Který odpovídá zástupné procedury funkce akcelerátoru pro hledání.  
  
 `tagValue`  
 [in] Hodnota ukazatele značka.  
  
 `rva`  
 [in] Relativní virtuální adresu.  
  
 `ppResult`  
 [out] Ukazatel `IDiaEnumSymbols` ukazatel rozhraní, který je inicializován s výsledkem.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu volat jenom na `IDiaSymbol` rozhraní, které odpovídá funkci se zakázaným inzerováním akcelerátoru.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)