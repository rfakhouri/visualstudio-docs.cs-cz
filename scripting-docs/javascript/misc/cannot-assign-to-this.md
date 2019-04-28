---
title: Nelze přiřadit 'this' | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a4ba5d852a7d131a88930dd66931c026074549b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946586"
---
# <a name="cannot-assign-to-this"></a>Nelze přiřazovat do objektu 'this'
Pokusili jste se přiřadit hodnotu **to**. **to** je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] – klíčové slovo, který odkazuje na buď:

- objekt aktuálně provádění metody,

- globální objekt, pokud neexistuje žádná metoda aktuální (nebo metoda nepatří do jiného objektu).

Metoda je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] funkci, která prostřednictvím objektu, který je vyvolána. Uvnitř metody **to** – klíčové slovo je odkaz na objekt vyvolání metody prostřednictvím (Probíhá bude objekt vytvořený pomocí volání konstruktoru třídy s **nové** operátor).

Uvnitř metody, můžete použít **to** k odkazování na aktuální objekt, ale nelze přiřadit novou hodnotu **to**.

## <a name="to-correct-this-error"></a>Oprava této chyby

- Nepokoušejte se přiřadit **to**. Pro přístup k vlastnosti nebo metody instance objektu, pomocí operátoru tečka (například **circle.radius**).

  > [!NOTE]
  > Nelze pojmenovat proměnnou uživatel vytvořil **to**; je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] vyhrazené slovo.

## <a name="see-also"></a>Viz také

- [this – příkaz](../../javascript/reference/this-statement-javascript.md)
- [Řešení potíží se skripty](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)