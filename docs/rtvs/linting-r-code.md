---
title: Kód linting R
description: Jak pracovat s podporou linting sestavení v sadě Visual Studio pro R, včetně možnosti linting.
ms.date: 01/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
f1_keywords:
- vs.toolsoptionspages.text_editor.r.lint
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: e5494283fdf759ddc664207d62d40f7f83993632
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031849"
---
# <a name="linting-r-code-in-visual-studio"></a>Linting R kódu v sadě Visual Studio

Linting analyzuje kód na nich možné chyby, formátování problémů a obdobný kód například nesprávné prázdný znak. Linting také pomáhá podporovat určité konvence psaní kódu, například jak jsou pojmenované identifikátory. Takové konvence jsou užitečné v rámci týmů a jiných spolupráce situacích.

R Tools pro Visual Studio (RTVS) poskytuje integrované linting pro R a chování, které jsou řízeny prostřednictvím nejrůznějších možností, které jsou popsané v tomto článku. Tyto možnosti se nacházejí v **nástroje > Možnosti > textový Editor > R > hadříkem**.

Linting ve výchozím nastavení vypnutá. Chcete-li povolit linting, nastavte **všechny > Povolit hadříkem** možnost na hodnotu true.

Když je povolené, linting se použije v editoru během psaní. Problémy se zobrazí jako zelená podtržení vlnovkou. Na následujícím obrázku, například RTVS identifikovala šesti linting problémy, včetně použití `=` místo `<-` pro přiřazení, nedostatečná mezery okolo argumenty funkce, použijte pascalcase a velká písmena identifikátorů a použití středník. Ukazatele myši problém obsahuje popis.

![Příklady linting pro kód R](media/linting-01.png)

Často mění linting možnosti v závislosti na potřebách projektu nebo souboru. Například může použít ukázkový kód z kurzu online `=` místo `<-` společně s pascalcase identifikátory. Takový kód by zobrazit časté linting upozornění, protože výchozí možnosti linting příznak těchto případech. Při práci s tímto kódem, pak můžete zakázat možnosti místo výdaje čas odstranění každá instance.

## <a name="assignment-group"></a>Přiřazení skupiny

| Možnost | Výchozí hodnota | Vliv linting |
| --- | --- | --- |
| Vynucení \<- | `True` | Určuje, kdy `<-` nepoužívá pro přiřazení. |

## <a name="naming-group"></a>Názvy skupiny

Tyto identifikátory příznak možnosti, které používají různé zásady vytváření názvů:

| Možnost | Výchozí hodnota | Vliv linting |
| --- | --- | --- |
| Příznak camelCase | `False` | Identifikátory příznaky, které používají camelCase. |
| Dlouhé názvy příznak | `False` | Flags – identifikátory jejichž pojmenované být delší než nastavení "Maximální délka názvu". |
| Příznak několik teček | `True` | Příznaky identifikátory, které používají více tečky. |
| Příznak PascalCase | `True` | Identifikátory příznaky, které používají PascalCase. |
| Příznak snake_case | `False` | Identifikátory příznaky, které používají podtržítka. |
| Příznak velká písmena | `True` | Identifikátory příznaky, které používají velká písmena. |
| Maximální délka názvu | 32 | Délka aplikuje s "příznak dlouhé názvy" nastavení. |

## <a name="spacing-group"></a>Mezery skupiny

Tyto možnosti, které jsou nastaveny na `True` ve výchozím nastavení, řídit, kde linter identifikuje problémy mezery: po názvy funkcí kolem čárky kolem operátory otvírání a zavírání složené pozic místo před (a místo uvnitř ().

## <a name="statements-group"></a>Příkazy skupiny

| Možnost | Výchozí hodnota | Vliv linting |
| --- | --- | --- |
| Několik | `True` | Určuje, kdy se více příkazů jsou na stejném řádku. |
| Středníky | `True` | Identifikuje používá středníky. |

## <a name="text-group"></a>Text skupiny

| Možnost | Výchozí hodnota | Vliv linting |
| --- | --- | --- |
| Omezení délky řádku | `False` | Nastaví, zda linter flags řádky delší než možnost "Maximální délka řádku". |
| Maximální délka řádku | 80 | Nastaví délku řádku použít tak možnost "Maximální délku řádku". |

## <a name="whitespace-group"></a>Prázdné skupiny

Tyto možnosti, které jsou nastaveny na `True` ve výchozím nastavení, řídit, kde linter identifikuje problémy prázdné: použití karet, použijte dvojité uvozovky, koncové prázdné řádky a koncové mezery.