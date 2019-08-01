---
title: Přidat kontroly null pro všechny (parametry)
ms.date: 07/24/2019
ms.topic: reference
author: stcahlon
ms.author: t-shzach
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: da3a616844dbe914cfe796ec35d1501bf83dd1ef
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/01/2019
ms.locfileid: "68713346"
---
# <a name="add-null-checks-for-all-parameters"></a>Přidat kontroly null pro všechny parametry 

Tento refaktoring platí pro: 

- C# 

**Co:** Vytvoří a přidá `if` příkazy, které kontrolují hodnotu null všech nezaškrtnutých parametrů s možnou hodnotou null. 

**Kdy:** Chcete rychle přidat kontroly hodnoty null u všech použitelných parametrů metody.

**Proč:** Zápis prázdných kontrol pro mnoho parametrů může být časově náročný a opakující se. Použití tohoto refaktoringu je rychlé a díky tomu je program robustnější.  

## <a name="how-to"></a>Postupy 

1. Umístěte kurzor na libovolný parametr v rámci metody.

2. Stisknutím klávesy **Ctrl**+ **.** aktivační událost **rychlé akce a Refaktoringy** nabídky.

   ![Rychlé akce a refaktoringy](media/add-null-checks-for-all-parameters.png)
   
3. Tuto možnost vyberte, pokud chcete **pro všechny parametry přidat kontroly hodnoty null**.

   ![Přidat kontroly null pro všechny](media/add-null-checks-for-all.png) 

## <a name="see-also"></a>Viz také: 

- [Refactoring](../refactoring-in-visual-studio.md) 
