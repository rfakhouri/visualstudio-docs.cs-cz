---
title: Idiasession::findsymbolbyva – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findSymbolByVA method
ms.assetid: 0350df23-9a5d-4e8d-8c26-7f571d8fb1af
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 238b1998991b36004c95613be83c03d8ff04508e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673614"
---
# <a name="idiasessionfindsymbolbyva"></a>IDiaSession::findSymbolByVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasession::findsymbolbyva –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findsymbolbyva).  
  
Načte typ zadaný symbol, který obsahuje, nebo je nejblíže zadanou virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findSymbolByVA (   
   ULONGLONG    va,  
   SymTagEnum   symtag,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `va`  
 [in] Určuje virtuální adresu.  
  
 `symtag`  
 [in] Typ symbolu, která se má najít. Hodnoty pocházejí ze [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčtu.  
  
 `ppSymbol`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) načíst objekt představující symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
  
```cpp#  
IDiaSymbol* pFunc;  
pSession->findSymbolByVA( va, SymTagFunction, &pFunc );  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)



