---
title: Byla očekávána logická hodnota | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 261cf0ad93208c0eac09e42dcd68853352318e88
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817897"
---
# <a name="boolean-expected"></a>Byla očekávána logická hodnota
Pokusili jste se vyvolat **Boolean.prototype.toString** nebo **Boolean.prototype.valueOf** metodu na objekt typu než `Boolean`. Objekt tohoto typu volání musí být typu `Boolean`. Příklad:

```JavaScript
var o = new Object;
o.f = Boolean.prototype.toString;
o.f();
```

## <a name="to-correct-this-error"></a>Oprava této chyby

- Vyvolat pouze **Boolean.prototype.toString** nebo **Boolean.prototype.valueOf** metod u objektů typu **Boolean.**

## <a name="see-also"></a>Viz také

- [Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)
- [Datové typy](../../javascript/data-types-javascript.md)
- [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)
- [Kopírování, předávání a porovnávání dat](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)