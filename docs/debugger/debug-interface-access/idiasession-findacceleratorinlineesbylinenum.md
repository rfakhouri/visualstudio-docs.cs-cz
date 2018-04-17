---
title: IDiaSession::findAcceleratorInlineesByLinenum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c5d52dfb474175a3db72325b4739f118d1af0d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
Vrátí výčet symboly pro vložené rámce, které odpovídají zadaným zdrojovým umístěním.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [v] `IDiaSymbol` Odpovídající funkce se zakázaným inzerováním akcelerátoru, která musí být prohledán.  
  
 `file`  
 [v] `IDiaSourceFile` Umístění zdroje.  
  
 `linenum`  
 [v] Číslo řádku umístění zdroje.  
  
 `colnum`  
 [v] Číslo sloupce umístění zdroje.  
  
 `ppResult`  
 [out] Ukazatel na `IDiaEnumLineNumbers` ukazatel rozhraní, který je inicializován s výsledek.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)