---
title: IDiaSession::findSymbolsForAcceleratorPointerTag | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 95fd5e7a-c637-437e-b369-c864eef733c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14a601143161ed17961ae5efd22cdc14c3fbb923
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54924386"
---
# <a name="idiasessionfindsymbolsforacceleratorpointertag"></a>IDiaSession::findSymbolsForAcceleratorPointerTag
Vrátí výčet symboly proměnné, která odpovídá hodnotě zadané značky v nadřazeném prvku. funkce se zakázaným inzerováním akcelerátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findSymbolsForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [in] Idiasymbol –, která odpovídá funkci akcelerátoru zástupné procedury pro hledání.  
  
 `tagValue`  
 [in] Hodnota ukazatele značka.  
  
 `ppResult`  
 [out] Ukazatel `IDiaEnumSymbols` ukazatel rozhraní, který je inicializován s výsledkem.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)