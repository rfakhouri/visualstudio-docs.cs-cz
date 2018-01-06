---
title: "Linting R kód R nástroje pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords: vs.toolsoptionspages.text_editor.r.lint
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 76f4ceb040e62e4ebac46e8a791f5dac0d73aff5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="linting-r-code-in-visual-studio"></a>Linting R kódu v sadě Visual Studio

Linting je proces, který analyzuje kód na nich možné chyby a také formátování problémy a dalších šumu v souborech kódu (například nesprávné prázdných znaků). Linting také pomáhá podporovat určité konvence psaní kódu, například přidělování identifikátorů názvů, což je velmi užitečné v rámci týmů a jiných spolupráce situacích.

R nástrojů pro Visual Studio (RTVS) poskytuje integrovanou linting pro R a chování, které jsou řízeny prostřednictvím nejrůznějších možností. Tyto možnosti se nacházejí v **nástroje > Možnosti > textový Editor > R > hadříkem**.

Linting ve výchozím nastavení vypnutá. Chcete-li povolit linting, nastavte **všechny > Povolit hadříkem** možnost na hodnotu true. Následující části v tomto tématu popisují všemi dalšími možnostmi linting:

Když je povolené, linting se použije v editoru během psaní. Problémy se zobrazí jako zelená podtržení vlnovkou. Na následujícím obrázku, například RTVS identifikovala šesti linting problémy, včetně použití `=` místo `<-` pro přiřazení, nedostatečná mezery okolo argumenty funkce, použijte pascalcase a velká písmena identifikátorů a použití středník. Ukazatele myši problém obsahuje popis.

![Příklady linting pro kód R](media/linting-01.png)

## <a name="assignment-group"></a>Přiřazení skupiny

| Možnost | Výchozí hodnota | Vliv linting |
| --- | --- | --- |
| Vynucení\<- | `True` | Určuje, kdy `<-` nepoužívá pro přiřazení. |

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