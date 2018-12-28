---
title: Nelze přiřadit 'this' | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f47778075b0395e4f0791d8f485188d40fab87a4
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802589"
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