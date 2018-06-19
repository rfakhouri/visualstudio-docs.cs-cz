---
title: Idiasession::get_loadaddress – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::get_loadAddress method
ms.assetid: 5162ae1a-38e3-4571-8995-4ed9be1dec3e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 88ba73b7d848388d1f4b5c039723243690345517
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461594"
---
# <a name="idiasessiongetloadaddress"></a>IDiaSession::get_loadAddress
Načte adresu zatížení pro spustitelný soubor, který odpovídá symboly v tomto úložišti symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_loadAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí virtuální adresy (VA), kde je načtena na soubor .exe nebo .dll souboru.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Adresa vrácený zatížení je vždy nula. Pokud konkrétně nastavit pomocí [idiasession::put_loadaddress –](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::put_loadAddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)