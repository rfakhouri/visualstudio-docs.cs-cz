---
title: Funkce ArrayBuffer.isView (ArrayBuffer) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1887324f-892b-4fcd-ad33-748ba9517a06
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5aaae2acb38aa2f8c4b5e49ea203e86665315700
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788856"
---
# <a name="arraybufferisview-function-arraybuffer"></a>Funkce ArrayBuffer.isView (ArrayBuffer)
Určuje, zda objekt obsahuje zobrazení vyrovnávací paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
ArrayBuffer.isView(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který se má ověřit  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud platí některá z následujících akcí:  
  
-   `object`je `DataView` objektu.  
  
-   `object`je typované pole.  
  
 Jinak, vrátí metoda `false`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `isView` funkce k testování typované pole a `DataView` objektu.  
  
```JavaScript  
var uint = new UInt8ClampedArray(10);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(uint) ); // Outputs true  
{  
var dataView = new DataView(uint.buffer);  
  
if(console && console.log) {  
    console.log( ArrayBuffer.isView(dataView) ); // Outputs true.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Objekt Uint8ClampedArray](../../javascript/reference/uint8clampedarray-object-javascript.md)