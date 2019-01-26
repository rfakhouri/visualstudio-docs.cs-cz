---
title: Omezení ladění skriptů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASPX breakpoint mapping, limitations
- script debugging, limitations
- breakpoint mapping, limitations
ms.assetid: 280eead5-693c-47af-967f-dfe9d23f84db
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a4c74a698a07718d99036ee4fc23c5b45123b9dc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55021556"
---
# <a name="limitations-on-script-debugging"></a>Omezení ladění skriptů
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podporuje ladění skriptů na straně klienta, v souladu s omezeními v tomto tématu.  
  
## <a name="limitations-on-breakpoint-mapping-with-client-side-script"></a>Omezení mapování zarážek pomocí skriptu na straně klienta  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Umožňuje nastavit zarážku na straně serveru ASPX nebo HTML soubor, který se transformuje do souboru na straně klienta v době běhu. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mapuje zarážku ze souboru na straně serveru pro odpovídající zarážky v souboru straně klienta, v souladu s těmito omezeními:  
  
-   Zarážky nastavené v `<script>` bloky. Zarážky v zpracování vloženého skriptu nebo `<% %>` bloky nelze mapovat.  
  
-   Adresa URL prohlížeče na stránce musí obsahovat název stránky. Například, http://microsoft.com/default.apsx. Mapování zarážek nemůže rozpoznat jako například přesměrování z adresy http://microsoft.com na výchozí stránku.  
  
-   Zarážky musí být nastavena na stránce určeného v adrese URL prohlížeče, nikoli v souboru ASPX ovládací prvek (ascx), hlavní stránky nebo jiný soubor součástí této stránce. Zarážky nastavené v zahrnuté stránky nelze mapovat.  
  
-   Zarážky nastavené v `<script defer=true>` bloky nelze mapovat.  
  
-   Pro zarážky nastavené v `<script id="">` bloky, ignoruje mapování zarážek `id` atribut.  
  
## <a name="breakpoint-mapping-and-duplicate-lines"></a>Mapování zarážek a duplicitní řádky  
 Algoritmus mapování zarážek ve skriptu na straně serveru a na straně klienta najít odpovídající umístění, kontroluje kód na každém řádku. Algoritmus předpokládá, že každý řádek představuje jedinečný. Pokud dva nebo více řádky obsahují stejný kód a nastavte zarážku v jednom z těchto duplicitní řádky, algoritmus mapování zarážky vybrat nesprávné duplicitní v souboru straně klienta. Chcete-li tomu zabránit, přidejte komentář k řádku, kde jste nastavili zarážku. Příklad:  
  
```csharp
i++ ;  
i ++; // I added a comment, so this line is now unique  
i ++;  
```
