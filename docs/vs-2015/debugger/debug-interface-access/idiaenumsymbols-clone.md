---
title: Idiaenumsymbols::clone – | Dokumentace Microsoftu
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
- IDiaEnumSymbols::Clone method
ms.assetid: 5c542025-98cf-4307-901f-b9430f780cf0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e5ae16b6363d0f55171cbfd52770aebc639edf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672392"
---
# <a name="idiaenumsymbolsclone"></a>IDiaEnumSymbols::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumsymbols::clone –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsymbols-clone).  
  
Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSymbols** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppenum  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) objekt, který obsahuje duplicitní čítače výčtu. Symboly nejsou duplicitní, pouze enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)



