---
title: IDiaSession::findAcceleratorInlineesByName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a13400cab447f4122a88bfbcec1265ae8e7e2fd5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53828092"
---
# <a name="idiasessionfindacceleratorinlineesbyname"></a>IDiaSession::findAcceleratorInlineesByName
Vrátí výčet symbolů pro vložené rámce odpovídající názvu funkce zadány jako vložené.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `name`  
 [in] Název funkce inlinee chcete prohledat.  
  
 `option`  
 [in] Možnosti hledání název se použije při vyhledávání vložený snímků, které odpovídají `name`. Další informace najdete v tématu [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md).  
  
 `ppResult`  
 [out] Ukazatel `IDiaEnumSymbols` ukazatel rozhraní, který je inicializován s výsledkem.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce hledá inlinees pouze v rámci akcelerátoru zástupné procedury funkcí. Nativní C++ postup záznamů je ignorován.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)