---
title: IDiaSession::findSymbolsForAcceleratorPointerTag | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 95fd5e7a-c637-437e-b369-c864eef733c2
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 55e69ae6380faa58d2b63074734cfe3c065759e7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196346"
---
# <a name="idiasessionfindsymbolsforacceleratorpointertag"></a>IDiaSession::findSymbolsForAcceleratorPointerTag
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vrátí výčet symboly proměnné, která odpovídá hodnotě zadané značky v nadřazeném prvku. funkce se zakázaným inzerováním akcelerátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
