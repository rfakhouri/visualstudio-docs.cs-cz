---
title: Ijsdebugdatatarget::readnullterminatedstring – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.ReadNullTerminatedString
apilocation:
- jscript9diag.dll
ms.assetid: 64683b39-6fc2-40c4-82ae-2a6f58d392d5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 178a2d3705e4904de9253c02319f6ba94e567d76
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62582361"
---
# <a name="ijsdebugdatatargetreadnullterminatedstring-method"></a>IJsDebugDataTarget::ReadNullTerminatedString – metoda
Přečte zadaný počet znaků z cíle.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ReadNullTerminatedString(  
   UINT64 address,  
   UINT16 characterSize,  
   UINT32 maxCharacters,  
   BSTR *pString  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] Adresa pro čtení z.  
  
 `characterSize`  
 [in] velikost každého znaku v řetězci  
  
 `maxCharacters`  
 [in] Maximální počet znaků pro čtení. Hodnota maxCharacters by měla být přiměřená. Každá žádost o více než 128MB paměti se nezdaří.  Pokud řetězec je větší než vlastnost maxCharacters, bude výsledný řetězec zkrácen po maxCharacters.  
  
 `pString`  
 [out] Čtení BSTR z cíle.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Vrátí S_FALSE v případě zkrácen.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)