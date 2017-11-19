---
title: "Jscreatetypedarray – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1df33d0e1aadec9d7ed5aebf743e2c2f840e51fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatetypedarray-function"></a>JsCreateTypedArray – funkce
Vytvoří objekt typované pole JavaScript.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayType`  
 Typ pole pro vytvoření.  
  
 `baseArray`  
 Základní pole nové pole. Použití `JS_INVALID_REFERENCE` Pokud žádné základní pole.  
  
 `byteOffset`  
 Posun v bajtech od začátku `baseArray` (`ArrayBuffer`) pro výsledek typu pole odkazovat. Platí jenom v případě `baseArray` je `ArrayBuffer` objektu. Musí být 0. v opačném případě.  
  
 `elementLength`  
 Počet prvků v poli. Platí jenom při vytváření nového typu pole bez `baseArray` (`baseArray` je `JS_INVALID_REFERENCE`) nebo pokud `baseArray` je `ArrayBuffer` objektu. Musí být 0. v opačném případě.  
  
 `result`  
 Nový objekt typu pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `baseArray` Může být `ArrayBuffer`, jiného typu pole nebo JavaScript `Array`. Pole vráceného typu použije `baseArray` Pokud se jedná `ArrayBuffer`, nebo jinak vytvořit a použít kopii základní zdrojové pole.  
  
 Vyžaduje aktivní kontext skriptu.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)