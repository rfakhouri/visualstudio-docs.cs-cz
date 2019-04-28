---
title: Idiaenumsourcefiles::get__newenum – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::get__NewEnum method
ms.assetid: 8405966c-64b4-4743-9a83-0e27ca2047c7
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2460194426384d574cf2dbd36d89819d38472f14
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62829651"
---
# <a name="idiaenumsourcefilesgetnewenum"></a>IDiaEnumSourceFiles::get__NewEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `IUnknown` rozhraní zastupující <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> verzi výčet.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)
